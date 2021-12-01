# Ubuntu Eenvironment Ssetup For laravel


Before Running Any Command You Need To Run

```
 sudo apt update
```

# Curl

### Install

```
sudo apt install curl
```

# PHP

### Install

```
sudo apt install php-fpm
```
### Install 7.4

```
sudo apt install php7.4-fpm
```

To check the status of the service, run

```
systemctl status php7.4-fpm
```

### Link

- [Visit Here](https://linuxize.com/post/how-to-install-php-on-ubuntu-20-04)

# Composer

### Install

```
curl -sS https://getcomposer.org/installer -o composer-setup.php
```

```
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

### Link

- [Visit Here](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-20-04)

# Valet

### Install
```
sudo apt-get install php7.4-curl
```

```
sudo apt-get install network-manager libnss3-tools jq xsel
```

```
composer global require cpriego/valet-linux
```

```
test -d ~/.composer && bash ~/.composer/vendor/bin/valet install || bash ~/.config/composer/vendor/bin/valet install
```

### Link

- [Cara Install Laravel Valet di Linux](https://www.susantokun.com/cara-install-laravel-valet-di-linux/)
- [Valet Linux Faq](https://cpriego.github.io/valet-linux/faq)

# Mysql-Server

### Install

```
sudo apt install mysql-server -y
```

```
sudo mysql
```

### Update Password

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'P@ssw0rd';
```

```
FLUSH PRIVILEGES;
```

```
exit
```

### Link

- [Visit Here](https://www.youtube.com/watch?v=cyNLSlL-BXQ&t=244s)

# phpmyadmin

### Install

```
sudo apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```

### Link

- [How To Install and Secure phpMyAdmin on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-ubuntu-20-04`)

### Symlink

```
ln -s /usr/share/phpmyadmin /var/www/phpmyadmin
```

### Link

- [Symlink Github](https://gist.github.com/MnMTech/2cb40b6bf892c22eac26)

# Node Js

### Install

```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```

```
sudo apt install nodejs
```

### Link

https://linuxize.com/post/how-to-install-node-js-on-ubuntu-18.04/

### Update

```
sudo n latest
```

### Fix PATH:

```
sudo apt-get install --reinstall nodejs-legacy     # fix /usr/bin/node
```

### Link
- [Visit Link](https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version)

