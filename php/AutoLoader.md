* Class statique avec une méthode statique Register que j'appelle pour éviter les Require de 10 class.
* DIRNAME étant le nom du dossier contenant toutes les classes.

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
require 'DIRNAME/AutoLoader.php';
AutoLoader::Register();
```
