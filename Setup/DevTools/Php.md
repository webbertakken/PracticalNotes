# Setup PHP

## Windows
- Download php at [php.net/download 🗗](https://php.net/download)
- Extract the contents of the archive to a folder (e.g. `x:/php`)
- Change the `php.ini-development` to `php.ini`
- Add the folder to the %PATH% environment variable (requires restart)
- Check the php version by running `php -v`

#### Enable extensions

```ini
; Enable one of these 2 lines to set the extension directory relative to the php binary
; On unix/osx
;extension_dir = "./"
; On windows:
;extension_dir = "ext"
```

- Enable required plugins by removing the `;` sign before the extensions

___Note:__ do not use `php_<ext>.dll` or `<ext>.so`, but instead just use `<ext>`.

```ini
extension=intl
extension=mbstring
extension=openssl
extension=pdo_mysql
extension=pdo_sqlite
extension=php_xsl
```

#### Performance settings

```ini
[PHP]
realpath_cache_size = 5M

[opcache]
opcache.enable=1
opcache.memory_consumption=512
opcache.max_accelerated_files=10000
opcache.validate_timestamps=1
opcache.revalidate_freq=1
```

#### XDebug
- Download at [https://xdebug.org/download.php 🗗](https://xdebug.org/download.php)
- Rename the dll to php_xdebug.dll and add it to the ext folder within php
- Enable the extension adding this to php.ini (locate by running `php --ini`)
- Change the extension path to reflect your OS and installation

```ini
[xdebug]
; full path to the xdebug library
zend_extension = C:\php\ext\php_xdebug.dll
; stack traces will be shown by default on an error event. You can disable showing stacktraces from your code with xdebug_disable()
xdebug.default_enable = 1
; errors will always be displayed, no matter what the setting of PHP's display_errors is
xdebug.force_display_errors = 1
; force certain errors from being shown no matter what an application does with ini_set()
xdebug.force_error_reporting = 1
```

## Bash (WSL)
```bash
$ sudo apt-get install python-software-properties
$ sudo add-apt-repository ppa:ondrej/php
$ sudo apt-get update
$ sudo apt-get install -y php7.2
```

Check if the version is what we're expecting
```bash
$ php -v
```

Search for the packages that you need
```bash
$ sudo apt-cache search php7.2
```

Install most common php packages
```bash
$ sudo apt-get install php7.2-common \
    php7.2-apcu \
    php7.2-curl \
    php7.2-gd \
    php7.2-imagick \
    php7.2-json \
    php7.2-intl \
    php7.2-mbstring \
    php7.2-opcache \
    php7.2-xml \
    php7.2-zip
```

## Composer
- Go to the folder where you want Composer installed
- Look up and run the commands to run at [https://getcomposer.org/download/ 🗗](https://getcomposer.org/download/)
- (Windows only) Create a `composer.bat` file in the same folder and add the following contents:
```batch
@ECHO OFF
php "%~dp0composer.phar" %*
```
- Add the folder to the %PATH% environment variable (requires restart)
- Verify by running:
```bash
$ composer --version
```

## Symfony
Note: Symfony4 uses composer to create its project, for Symfony3 or earlier follow these steps:

- Go to the folder where you want Symfony-CLI installed
- Look up the commands to run at
[https://github.com/symfony/symfony-installer 🗗](https://github.com/symfony/symfony-installer)
- Run the commands
- (Windows only) Create a `symfony.bat` file in the same folder and add the following contents:
```batch
@ECHO OFF
php "%~dp0symfony" %*
```
