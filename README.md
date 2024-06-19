# Ubuntu Environment Setup For Laravel


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

### Install With Nginx

### Install 7.4

```
sudo apt install php7.4-fpm
```

To check the status of the service, run

```
systemctl status php7.4-fpm
```

### Install 8.0
```
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
```
```
sudo apt install php8.0-fpm
```

To check the status of the service, run

```
systemctl status php8.0-fpm
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


### UnInstall
```
rm -r /usr/local/bin/composer
```

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
- [8.1-fpm](https://www.cloudbooklet.com/how-to-install-php-fpm-with-apache-on-ubuntu-20-04)


# Valet Linux Plus
Before installing valet-linux-plus, install mysql-server, php extensions, redis-server.

### Install

```
composer global require genesisweb/valet-linux-plus 
```
```
sudo apt-get install libnss3-tools jq xsel
```
```
test -d ~/.composer && bash ~/.composer/vendor/bin/valet install || bash ~/.config/composer/vendor/bin/valet install
```
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
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

```
sudo apt install nodejs
```

### Link

https://linuxize.com/post/how-to-install-node-js-on-ubuntu-18.04/

### Update

```
sudo npm cache clean -f
sudo npm install -g n
```
### Stable Version
```
sudo n stable
```
### Latest Version
```
sudo n latest
```

### Link
- [Visit Link](https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version)


### Downgrade NPM
```
npm install -g npm@8.19.2
```
### Link
- [Visit Link](https://www.devopsschool.com/blog/how-to-downgrade-npm-version)

### Install PNPM

```
sudo npm install -g pnpm
```
# oh-my-zsh

### Install

```
sudo apt install zsh
```

Make default shell

```
chsh -s $(which zsh)
```

Install

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Install PowerLeve10K theme

```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Download Plugins for autosuggestion and syntax highlighting

```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

Now edit `~/.zshrc` file to use the PowerLeve10K theme, Awesome

```
snap install micro --classic
```

```
micro ~/.zshrc
```

Find the `ZSH_THME` and replace it with

```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Now we will add plugins\
`plugins=(git)`

```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

Save And Exit. Then Set The Terminal Design

### Link

- [Make your terminal beautiful and fast with ZSH shell and PowerLevel10K](https://medium.com/@shivam1/make-your-terminal-beautiful-and-fast-with-zsh-shell-and-powerlevel10k-6484461c6efb)

### Install Meslo Nerd Font
- [powerlevel10k](https://github.com/romkatv/powerlevel10k)

Change Font From Terminal Preferences To
- MesloLGS NF Regular 
### Uninstall

`.oh-my-zsh`\
 `ls`\
 `tools`\
 `ls`\
 `sh uninstall.sh`\
 `y`

### Link

- [Uninstall Oh My Zsh from Kali Linux](https://www.youtube.com/watch?v=L1gRxcykSb8)



# Docker


## Uninstall old versions
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```

### Install

```
sudo apt-get update
```
```
sudo apt-get install \ ca-certificates \ curl \ gnupg \ lsb-release
```

### Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

### Use the following command to set up the stable repository

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```


### Install Docker Engine
```
sudo apt-get update
```
```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

### Verify that Docker Engine is installed correctly by running the `hello-world` image

```
sudo docker run hello-world
```

### Install Docker Compose on Linux systems
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

### Test the installation
```
docker-compose --version
```


# Use Php 7.4 in 8
```
valet use 7.4 
```
```
valet use 7.4 --update-cli
```
### Composer Global update
```
composer global upgrade
```


## Extension
### PHP 7.4

```
sudo apt install php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap php7.4-zip php7.4-intl php7.4-bcmath -y
```
### PHP 8.0

```
sudo apt install php8.0-common php8.0-mysql php8.0-xml php8.0-xmlrpc php8.0-curl php8.0-gd php8.0-imagick php8.0-cli php8.0-dev php8.0-imap php8.0-mbstring php8.0-opcache php8.0-soap php8.0-zip php8.0-intl php8.0-bcmath -y
```
### PHP 8.1

```
sudo apt install php8.1-common php8.1-mysql php8.1-xml php8.1-xmlrpc php8.1-curl php8.1-gd php8.1-imagick php8.1-cli php8.1-dev php8.1-imap php8.1-mbstring php8.1-opcache php8.1-soap php8.1-zip php8.1-intl php8.1-bcmath -y
```

### PHP 8.2

```
sudo apt install php8.2-common php8.2-mysql php8.2-xml php8.2-xmlrpc php8.2-curl php8.2-gd php8.2-imagick php8.2-cli php8.2-dev php8.2-imap php8.2-mbstring php8.2-opcache php8.2-soap php8.2-zip php8.2-intl php8.2-bcmath -y
```

### PHP 8.3
```
sudo apt install php8.3-common php8.3-mysql php8.3-xml php8.3-xmlrpc php8.3-curl php8.3-gd php8.3-imagick php8.3-cli php8.3-dev php8.3-imap php8.3-mbstring php8.3-opcache php8.3-soap php8.3-zip php8.3-intl php8.3-bcmath -y
```

# Install Redis
```
sudo apt install redis-server
```

# Import Large Database (Sql) File with Terminal
```
mysql -u root -p
``` 
Enter Password :

```
use databasename;
```
```
source /home/username/Downloads/databasename.sql
```
