# php-filemode-patch
A patch for configure log file permission for php-fpm . 
=======

explantion 
---
This patch is used for configuration the permission of the log files of php-fpm.
php-fpm created log file with a default file permission of 0600(-rw- --- ---),which makes other user or group unable to 
read the log file . It's so inconvenient, so I come out with this patch ,which makes u able to congiure the log file 
permission u want.

howto
---
>
cd path-to-php-src && patch -p1 <filemode.patch 
>

then configurate  the php-fpm.conf file with directive in global section:

>
file_mode = 0644
>
;or other file permission u want.
>

service php-fpm restart 
>
