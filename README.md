# Carpetas
``` 
/var/www/html/wordpress
``` 



# Instalación de Wordpress en Linux
```  
apt-get update
apt-get install apache2
apt-get install mysql-server
apt-get install php php-mysql

mysql -u root -px1234567890

create database wordpress;
grant all privileges on wordpress.* to 'user'@'localhost' identified by 'user';
flush privileges;

wget https://es.wordpress.org/wordpress-latest-es_ES.tar.gz
tar -xzvf wordpress-latest-es_ES.tar.gz
rm wordpress-latest-es_ES.tar.gz
mv wordpress /var/www/html/
cd /var/www/html/wordpress
cp wp-config-sample.php wp-config.php
nano wp-config.php

'DB_NAME', 'DB_USER' y 'DB_PASSWORD',

chown -R www-data:www-data .


cd /etc/apache2/sites-available
cp 000-default.conf wordpress.conf
nano wordpress.conf 

<VirtualHost *:80>
 ServerName donwordpress.com
DocumentRoot /var/www/html/wordpress
 ErrorLog ${APACHE_LOG_DIR}/error.log
 CustomLog ${APACHE_LOG_DIR}/access.log combined
 </VirtualHost>
 
 
 a2ensite wordpress.conf
a2dissite 000-default.conf
systemctl restart apache2


```  
