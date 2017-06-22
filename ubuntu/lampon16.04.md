# Apache
```
root@cloud:~# apt-get install apache2
root@cloud:~# systemctl enable apache2
```
# MariaDB
```
root@cloud:~# apt-get install mariadb-server
```
Show MariaDB status
```
root@cloud:~# systemctl status mysql
```
Set root password
```
root@cloud:~# mysql_secure_installation
```
# PHP
```
root@cloud:~# apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0
root@cloud:/var/www/html# systemctl restart apache2
```
# phpMyAdmin
```
root@cloud:/var/www/html# apt-get install phpmyadmin
```
Create a user to login phpmyadmin
```
CREATE USER 'phpmyadmin'@'localhost' IDENTIFIED BY 'some_pass';
GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```
