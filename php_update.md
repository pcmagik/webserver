# APACHE

php -v


## Repository for debian:

apt install sudo

sudo apt-get update && sudo apt-get upgrade -y && sudo apt-get dist-upgrade -y && sudo apt-get autoremove

sudo apt install software-properties-common

sudo apt -y install lsb-release apt-transport-https ca-certificates

sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg

echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list

sudo apt-get update

sudo systemctl restart apache2

sudo a2dismod php7.4

sudo a2enmod php8.2

sudo systemctl restart apache2

sudo reboot


php -v


===========================================================================================
## APACHE OPTIMIZATION

sudo nano /etc/php/8.2/apache2/php.ini

opcache.memory_consumption=256

opcache.interned_strings_buffer=10

opcache.max_accelerated_files=50000

opcache.revalidate_freq=2

opcache.fast_shutdown=1

opcache.enable_cli=1


## from Emil Czypryński

upload_max_filesize 1024M

post_max_size 1024M

memory_limit 2048M

max_execution_time 300

max_input_time 300
