# Setup PHP

## Setting up PHP for Windows

- PHP: https://windows.php.net/download
- Enable required plugins

### XDebug: 
- Download at https://xdebug.org/download.php
- Rename the dll to php_xdebug.dll and add it to the ext folder within php
- Enable the extension adding this to php.ini (locate by running `php --ini`)

```ini
[xdebug]
zend_extension = C:\php\ext\php_xdebug.dll

```

