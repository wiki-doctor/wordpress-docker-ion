# wordpress-docker
wordpress docker compose with ioncube and sourceguardian

## who to conifg 
-- just open ```.env``` and set your environment

## who to start without PhpMyAdmin 
-- just run this command :
```docker compose up -d --build wp-web ```
## who to full start 
-- run this command :
``` docker compose  up -d ```

## who to INSTALL ioncub
 curl -o ioncube.tar.gz http://downloads3.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz
 
 tar -xvvzf ioncube.tar.gz
 
 mv ioncube/ioncube_loader_lin_8.1.so /usr/local/lib/php/extensions/*
 
 rm -Rf ioncube.tar.gz ioncube
 
 php_ext_dir="$(php -i | grep extension_dir | head -n1 | awk '{print $3}')"
 
 echo "zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-20151012/ioncube_loader_lin_8.1.so" >
 /usr/local/etc/php/conf.d/00_docker-php-ext-ioncube_loader_lin_8.1.ini
 
 echo "zend_extension = $php_ext_dir/ioncube_loader_lin_8.1.so" > /usr/local/etc/php/conf.d/00-ioncube.ini

## who to INSTALL soap        
 docker-php-ext-install soap

## who to INSTALL PDO    
 docker-php-ext-install pdo_mysql
 docker-php-ext-enable pdo_mysql
