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
- [8.1-fpm](https://www.cloudbooklet.com/how-to-install-php-fpm-with-apache-on-ubuntu-20-04)

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
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
sudo n latest
```

### Link
- [Visit Link](https://askubuntu.com/questions/426750/how-can-i-update-my-nodejs-to-the-latest-version)

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
or 
```
valet use php@7.4
```

## Extension
```
sudo apt install php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap php7.4-zip php7.4-intl -y
```