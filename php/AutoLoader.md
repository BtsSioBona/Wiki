* Class statique avec une méthode statique Register que j'appelle pour éviter les Require de 10 class.

```php
class AutoLoader
{
  static function Register(){
    spl_autoload_register(array(__CLASS__, 'AutoLoad'));
  }

  static function AutoLoad($class_name){
    require 'DIRNAME/' . $class_name . '.php';
  }
}
```


* Je l'appelle ensuite :
```php
require 'class/AutoLoader.php';
AutoLoader::Register();
```
