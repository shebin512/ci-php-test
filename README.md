# ci-php-test

## Install php 5.6.x
```sh
sudo apt -y update
sudo add-apt-repository ppa:ondrej/php
sudo apt -y update
sudo apt -y install php5.6 php5.6-mcrypt php5.6-mbstring php5.6-curl php5.6-cli php5.6-mysql php5.6-gd php5.6-intl php5.6-xsl php5.6-zip

#disable apache2
sudo update-rc.d apache2 remove  # to re-enable sudo update-rc.d apache2 defaults
```

## install composer
```sh
mkdir -p ~/bin
cd ~/bin
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
sudo mv composer.phar composer # OR for global access sudo mv composer.phar /usr/local/bin/composer 
```

## Git Repo Access
```sh
ssh-keygen -t rsa -C "jenkins"
cat /var/lib/jenkins/.ssh/id_rsa.pub  # copy the content and add it to GitHub
```
## Buil Script
```sh
~/bin/composer up
vendor/phpunit/phpunit/phpunit tests/CalculatorTest.php
```
