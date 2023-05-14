# NGINX

sudo apt install php8.1-fpm

php-fpm8.1 -v

sudo nano /etc/php/8.1/fpm/php.ini

upload_max_filesize = 32M 

post_max_size = 48M 

memory_limit = 256M 

max_execution_time = 600 

max_input_vars = 3000 

max_input_time = 1000


sudo service php8.1-fpm restart

systemctl restart apache2



sudo nano /etc/nginx/sites-available/your.conf

"fastcgi_pass unix:/run/php/php7.4-fpm.sock;"

zmienić na:

"fastcgi_pass unix:/run/php/php8.1-fpm.sock;"

sudo nginx -t

sudo service nginx restart
