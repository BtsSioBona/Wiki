## pour XAMPP
### XDebug notes :
- OS : Windows 10
- php -v : 
```bash
PHP 7.0.9 (cli) (built: Jul 20 2016 11:08:23) ( ZTS )
Copyright (c) 1997-2016 The PHP Group
Zend Engine v3.0.0, Copyright (c) 1998-2016 Zend Technologies
```

- XDEBUG V utilisé : [PHP 7.0 VC14 TS (32 bit)](https://xdebug.org/files/php_xdebug-2.4.1-7.0-vc14.dll)
  (SHA1: c651c0ea39ca7cd198ecbba1c049921d4e7511f9)
- php.ini : 
```bash
[XDebug]
zend_extension_ts = "C:\xampp\php\ext\php_xdebug.dll"
xdebug.remote_enable = 1
xdebug.remote_host = 127.0.0.1
xdebug.remote_connect_back = 1
xdebug.remote_port = 9000
xdebug.idekey = "PHPSTORM" // Mon propre IDE
xdebug.profiler_enable = 1
xdebug.remote_log = "C:\XAMPP\tmp\xdebug.log"
xdebug.remote_autostart = 1
```
