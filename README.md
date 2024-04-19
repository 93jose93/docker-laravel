
#Image Ubuntu 20.04 (LTS) x64
Size 1 vCPU
1GB / 25GB Disk




> sudo apt-get update

> mkdir web

> cd web

> git clone https://github.com/93jose93/docker-laravel.git

> cd docker-laravel

#instalar php 8.1

> sudo add-apt-repository ppa:ondrej/php

> sudo apt-get install php8.1 php8.1-cli php8.1-mbstring zip unzip

> sudo apt-get install php8.1-xml

> sudo apt-get install php8.1-curl

> sudo apt-get install php8.1-bcmath

#instalar docker

> sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt-get update

sudo apt-get install docker-ce

sudo systemctl status docker

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version

#################instalar composer vercion 2 para usar php 8
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

php -d allow_url_fopen=On composer-setup.php --install-dir=/usr/local/bin --filename=composer

php -r "unlink('composer-setup.php');"


export PATH="~/.config/composer/vendor/bin:$PATH"

composer global require laravel/installer
##############crear proyecto de laravel
creo un proyecto con laravel 10 y livewire

laravel new app --jet

##############detener apache 

sudo service apache2 stop

##############inicializar doker

docker-compose up -d --build

//ingresar con docker root
docker exec -u root -it app /bin/bash

chmod -R 777 /var/www/storage/logs
chown -R www:www /var/www/storage/logs

