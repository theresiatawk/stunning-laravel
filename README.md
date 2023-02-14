# Deploying a Laravel Website: 

## Checkpoint 1: 

### sudo command:
sudo stands for "super user do". It's a command that is primarily used for Unix-based operating systems such as Linus and macOS.
sudo allows authorized users to execute commands as another user, typically the root user, which has full system privileges. 
It is often used in shell scripts and other automated process to perform administrative tasks that require elevated privileges, such as installing software, modifying system settings, or accessing protected files. 
The syntax for using the sudo command is typically sudo [command].

Here are some common use cases of sudo:

* Installing and updating software
* Modifying system settings
* Accessing protected files
* Performing system maintenance tasks

### apt-get command: 
The apt-get command is a package management tool for Debian-based Linux distributions such as Ubuntu, which allows users to install, upgrade, and remove software packages on their system.

Here are some of the common use cases of apt-get:

* Installing new packages: apt-get install <package-name> can be used to download and install a new software package from the configured repositories.
* Upgrading packages: apt-get upgrade can be used to download and install the latest version of all packages on the system.
* Removing packages: apt-get remove <package-name> can be used to remove a package from the system.
* Updating package information: apt-get update can be used to refresh the package database on the system, so that the latest information about available packages can be retrieved.
* Resolving package dependencies: apt-get automatically resolves dependencies when installing or upgrading packages, ensuring that all required packages are installed on the system.
  
The apt-get command is a powerful tool for managing software packages on a Linux system, and is often used by system administrators to ensure that their servers have the latest security updates and software packages installed.

### commands used: 
```
sudo apt-get install apache2
```
```
sudo apt-get install mysql-server
```
```
sudo apt-get install php-mysql
```
```
sudo apt-get install php
```
```
sudo apt-get install libapache2-mod-php
```
```
sudo apt-get install php-mcrypt
```
```
sudo apt-get install php-pear
```
```
sudo apt-get install curl
```
```
sudo apt-get install php-curl
```
```
sudo apt-get install php-cli
```
```
sudo apt-get install git
```
```
sudo a2emod rewrite
```
```
sudo service apache2 restart
```

---
## Checkpoint 2:

### commands used: 
```
cd /var/www/html
```
```
pwd
```
```
sudo git clone https://github.com/theresiatawk/stunning-laravel.git
```
---
## Checkpoint 3:

### commands used:

The following command is incorrect: 
```
curl -sS https://getcomposer.org/installer | sudo php - - install-dir=/usr/local/bin - filename=composer
```
To correct it we ommit the space between dashes: 
```
curl -sS https://getcomposer.org/installer | sudo php -- install-dir=/usr/local/bin - filename=composer
```
```
sudo composer install
```
---
## Checkpoint 4:
### commands used: 
```
pwd
```
```
cat ./.env.example | sudo tee ./.env
```
Edit the .env file using vim and change the APP_NAME value to ScriptingProject:
```
sudo vim .env
```
Generate an APP_KEY:
```
sudo php artisan key:generate
```

---
## Checkpoint 5:
### commands used: 
```
apache2 -v
```
```
which apache2
```
```
cd ../../etc/apache2
```
```
ls
```
Edit the apache2.conf file using vim and add to it the following code 
`
<Directory /var/www/html/stunning-laravel/public>
Options Indexes FollowSymLinks
AllowOverride all
Require all granted
</Directory>
`:
```
sudo vim apache2.conf
```
```
cd sites-enabled
```
Edit the 000-default.conf file using vim and add to it the following code 
`
ServerAdmin webmaster@localhost
DocumentRoot /var/www/html/stunning-laravel/public/
`:
```
sudo vim 000-default.conf
```
```
sudo service apache2 restart
```
## Checkpoint 6:
### commands used:
The following command changes the group ownership of the "storage" and "bootstrap/cache" directories (including all files and subdirectories within them) to the "www-data" group.

Here's a breakdown of the command:

* "sudo" runs the command with administrative privileges
* "chgrp" is a command that changes the group ownership of a file or directory
* "-R" flag applies the permission changes recursively to all files and subdirectories within the specified directories
* "www-data" is a common group name used by web servers, such as Apache, to access and manage web content. By changing the group ownership of the "storage" and "bootstrap/cache" directories to "www-data", the web server can access and modify these directories without needing to be the owner.
* The "storage" directory is typically used by web applications to store files such as session data, logs, and cached data.
* The "bootstrap/cache" directory is used by the Laravel PHP framework to store compiled application files for faster performance.

```
sudo chgrp -R www-data storage bootstrap/cache
```
The following command grants read, write, and execute permissions to the owner and group of the "storage" and "bootstrap/cache" directories, as well as all files and subdirectories within them.

Here's a breakdown of the command:

* "sudo" runs the command with administrative privileges
* "chmod" is a command used to change the permissions of files and directories
* "-R" flag applies the permission changes recursively to all files and subdirectories within the specified directories
* "ug+rwx" grants read (r), write (w), and execute (x) permissions to the owner (u) and group (g) of the directories
* "storage bootstrap/cache" specifies the directories to which the permissions are being applied.
```
sudo chmod -R ug+rwx storage bootstrap/cache
```














<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**
- **[WebReinvent](https://webreinvent.com/?utm_source=laravel&utm_medium=github&utm_campaign=patreon-sponsors)**
- **[Lendio](https://lendio.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
