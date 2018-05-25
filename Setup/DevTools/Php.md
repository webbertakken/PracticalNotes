# Setup PHP

## Setting up PHP for Windows

- Download php at https://windows.php.net/download
- Extract the contents of the archive to a folder (e.g. `x:/php`)
- Change the `php.ini-development` to `php.ini`
- Add the folder to the %PATH% environment variable (might require restart)
- Check the php version by running `php -v`

### 

### Enable extensions
- Enable required plugins by removing the `;` sign before the extensions
```ini
# This line
;extension = extension_name
# Becomes this line
extension = extension_name
```

### XDebug: 
- Download at https://xdebug.org/download.php
- Rename the dll to php_xdebug.dll and add it to the ext folder within php
- Enable the extension adding this to php.ini (locate by running `php --ini`)

```ini
[xdebug]
zend_extension = C:\php\ext\php_xdebug.dll
; stack traces will be shown by default on an error event. You can disable showing stacktraces from your code with xdebug_disable()
xdebug.default_enable = 1
; errors will always be displayed, no matter what the setting of PHP's display_errors is
xdebug.force_display_errors = 1
; force certain errors from being shown no matter what an application does with ini_set()
xdebug.force_error_reporting = 1
; disable the @ (shut-up) operator so that notices, warnings and errors are no longer hidden.
xdebug.scream = 1 
; warnings get converted to errors
xdebug.halt_level = E_WARNING|E_NOTICE|E_USER_WARNING|E_USER_NOTICE
```

### Composer:
- Go to the folder where you want composer installed
- Look up the commands to run at https://getcomposer.org/download/
- Run the commands
- Create a `composer.bat` file in the same folder and add the following content:
```batch
@ECHO OFF
php "%~dp0composer.phar" %*
```
- Add the folder to the %PATH% environment variable

