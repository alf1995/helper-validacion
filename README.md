# Introducción

- Este es un helper creado para tener nuestras propias reglas de validacion independiente de codeigniter.

# Requerimientos
- Instalamos el paquete [Respect\Validation](https://respect-validation.readthedocs.io/en/latest/installation/)
- PHP 7.3 o superior
- Codeigniter 3

# Instalación
```php
  # Descargamos el archivo y los copiamos a nuestra carpeta helper.
  
  # En nuestro archivo config habilitamos la carga automatica de composer:
  $config['composer_autoload'] = 'vendor/autoload.php';
  
  # Habilitamos nuestro helper en el archivo autoload en la carpeta config:
  $autoload['helper'] = array('validacion');
  
  # En nuestro controlador podremos llamar nuestro helper:
  # valida_campo(variable,reglas,nombre del campo):
  
  $error = '';
  $error .= valida_campo($email, 'not_empty|email|minlength:5|maxlength:80', 'Correo');
  $error .= valida_campo($nombre, 'not_empty|minlength:2|maxlength:50', 'Nombre');
  $error .= valida_campo($clave, 'not_empty|minlength:5|maxlength:30', 'Contraseña');
  $error .= valida_campo($reclave, 'not_empty|minlength:5|maxlength:30', 'Verificar contraseña');
  $error .= valida_campo($clave, 'password::'.$reclave, 'Contraseña');
  var_dump($error);
  
```
