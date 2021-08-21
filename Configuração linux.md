

<p align="center"><img width="300" src="https://upload.wikimedia.org/wikipedia/commons/3/35/Tux.svg"></p>
<p align="center"><img width="300" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Logo-ubuntu_no%28r%29-black_orange-hex.svg/1920px-Logo-ubuntu_no%28r%29-black_orange-hex.svg.png"></p>


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
```bash
sudo apt install php-cli unzip
 ```

*************************************************************************

 ### Instalar Node.Js
```bash
 curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
```
```bash
 sudo apt install -y nodejs
 ```
 ```bash
 sudo npm install -g npm
 ```
*************************************************************************

### Instalar Composer
```bash
 cd ~
  ```

```bash
 sudo curl -sS https://getcomposer.org/installer -o composer-setup.php
```

```bash
 HASH=`curl -sS https://composer.github.io/installer.sig`
```
```bash
 echo $HASH
```

```bash
 php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
 ```

```bash
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
 ```

```bash
composer 
```


*************************************************************************

### Instalar Vue.Js
```bash
sudo npm install -g @vue/cli
```
*************************************************************************
### Instalar  Apache

```bash
sudo apt install apache2
```
*************************************************************************
### Instalar  e Configrar o MySql e o PhpMyAdmin
```bash
sudo apt install mysql-server
```

```bash
sudo apt install php libapache2-mod-php php-mysql
```
```bash
sudo mysql
```

```bash
SELECT user,authentication_string,plugin,host FROM mysql.user;
```

```bash
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
```

```bash
FLUSH PRIVILEGES;
```

```bash
SELECT user,authentication_string,plugin,host FROM mysql.user;
```

```bash
exit
```

```bash
mysql -u root -p
```

```bash
sudo apt install phpmyadmin
```



 sudo add-apt-repository ppa:ondrej/php
 

************************************************************************
### Instalação e Configuração GIT

* instalar o GIT
```bash
 sudo apt install git
 ```
 
 * Configura usuário git de forma global
```bash
git config --global user.name "Fulano de Tal"
```

```bash
 git config --global user.email fulanodetal@exemplo.pt
 ```

************************************************************************
### Reiniciar o computador para concluir a configuração 

```bash
 reboot
 ```


