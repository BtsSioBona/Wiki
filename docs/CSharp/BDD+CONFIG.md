### Class de connexion à la base de données
```php
<?php
class Connexion
{
    public $dbh; // Objet dbh

    private static $instance;

    private function __construct()
    {
        // Construction des infos
        // & Recupération depuis un fichier de config externe
        $dsn = 'mysql:host=' . Config::read('db.host') .
               ';dbname='    . Config::read('db.basename');
               // Au besoin :
               //';port='      . Config::read('db.port') .
               //';connect_timeout=15';
        // Recup du nom d'utilisateur
        $user = Config::read('db.user');
        // recup du pwd
        $password = Config::read('db.password');
        // Gestion des Options :
        $options[PDO::ATTR_ERRMODE] = PDO::ERRMODE_EXCEPTION;
        $options[PDO::MYSQL_ATTR_INIT_COMMAND] = "SET NAMES utf8";

                // Création du pdo
        $this->dbh = new PDO($dsn, $user, $password, $options);
    }
    // Singleton
    public static function getInstance()
    {
        if (!isset(self::$instance))
        {
            $object = __CLASS__;
            self::$instance = new $object;
        }
        return self::$instance;
    }
}
```

### Fichier de config pour les Data d'accés à la base de données.

```php
<?php
class Config
{
    static $confArray;

    public static function read($name)
    {
        return self::$confArray[$name];
    }

    public static function write($name, $value)
    {
        self::$confArray[$name] = $value;
    }

}

// db
Config::write('db.host', 'localhost'); // Entrez le nom du host
//Config::write('db.port', '0000'); // Entrez le port
Config::write('db.basename', 'DBNAME'); // Entrez le nom de la Base de données
Config::write('db.user', 'root'); // Entrez l'utilisateur de la Base de données
Config::write('db.password', 'toor'); // Entrez le mot de passe de l'utilisateur
$options[PDO::ATTR_ERRMODE] = PDO::ERRMODE_EXCEPTION; // OPTIONS
$options[PDO::MYSQL_ATTR_INIT_COMMAND] = "SET NAMES utf8"; // OPTIONS

```
