

<p align="center"><img width="300" src="https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg"></p>


## Configuração linux  para desenvolvimento web

 
 

 ### Preparação do sistema
*  Baixar aualização do sistema
```bash
sudo apt update 
```
* Instalar aualização do sistema
```bash
sudo apt upgrade
```




************************************************************************
### Instalar as Dependencias do PHP
* sudo apt install php-cli unzip
 

************************************************************************
### Instalar Git
* sudo apt install git
*************************************************************************

 ### Instalar Node.Jd
* curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
* sudo apt install -y nodejs
* sudo npm install -g npm
*************************************************************************

### Instalar Composer

* cd ~
* sudo curl -sS https://getcomposer.org/installer -o composer-setup.php
* HASH=`curl -sS https://composer.github.io/installer.sig`
* echo $HASH
* php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

* sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
* composer

*************************************************************************

npm install -g @vue/cli





sudo apt install apache2


sudo apt install mysql-server


sudo apt install php libapache2-mod-php php-mysql


sudo mysql
SELECT user,authentication_string,plugin,host FROM mysql.user;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
FLUSH PRIVILEGES;
SELECT user,authentication_string,plugin,host FROM mysql.user;
exit
mysql -u root -p


sudo apt install phpmyadmin





