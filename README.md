# PHP-Snippets

## Check and change configuration settings 
To check configuration settings create a file info.php and upload to your server 
```php
<?php
phpinfo();
?>
```
When visiting the info.php file on your web server (http://www.example.com/info.php) you will see a page that displays details on the PHP environment, OS version, paths, and values of configuration settings. The file to the right of the **Loaded Configuration File** line shows the location of **php.ini** to edit in order to update your PHP settings.
### Edit php.ini
Lines that begin with ; are comments.

Edit the lines that you want to  change , save the file and restart webserver.

https://www.digitalocean.com/community/tutorials/how-to-change-your-php-settings-on-ubuntu-14-04

### Alternative
By changing .htaccess (with a leading dot) in the server document root folder on an Apache server.
Configuration directives that set a value are preceded by php_value.
Directives that turn a setting on or off are preceded by php_flag.
```
php_value error_reporting 32767
php_flag display_errors on
```
By setting values in your config php application
```php
<?php
ini_set('error_reporting', E_ALL);
ini_set('display_errors', '1');

// Time zone needs to be set only when using date-related functions
date_default_timezone_set('America/Los_Angeles');
```
If your server supports .user.ini files, save this file as .user.ini (with a leading dot) in the server document root.
The configuration directives use the same syntax as php.ini.
Lines beginning with a semicolon are ignored.
```
error_reporting E_ALL
display_errors = on

; Time zone setting for US West Coast
date.timezone = America/Los_Angeles
```

http://blog.koonk.com/2015/07/46-useful-php-code-snippets-that-can-help-you-with-your-php-projects/
