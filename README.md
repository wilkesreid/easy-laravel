Easy Laravel
==========

Get Laravel up and running from the terminal as quickly and easily as possible. Made for Mac.

## Software
- Nginx
- Mariadb (MySQL)
- Redis

## Requirements
- [Docker](https://docs.docker.com/engine/installation/)
- [Composer](https://getcomposer.org/download/)

## Installation
    $ git clone https://github.com/wilkesreid/easy-laravel laravel
    $ cd laravel
    $ ./install
- Visit localhost in your browser.

## Instructions

The `code` folder contains the Laravel files.

Type `./php_shell` to open the PHP terminal so you can use `php artisan` commands. If you try to use `php artisan` without typing `./php_shell` first, some features of Laravel won't work, like anything related to the database or cache.

Modify `site.conf` to change the nginx configuration, and then run `docker restart laravel_web_1` to apply the changes.

Modify `php.ini` to change the php configuration, and then run `docker restart laravel_php_` to apply the changes.

## Removing

    $ ./uninstall
    
This command will permanently remove everything from your system that was created from the `./install` command.

To stop Laravel without permanently deleting it, run `docker-compose down`.

## Issues

Docker containers have issues when it comes to mounted volumes shared with the host, especially when it comes to user/directory permissions. Laravel requires that the storage and bootstrap/cache directories are writable, but because those directories are being shared between the host and php container, there are issues. The `./install` command sets the permissions to 777 initially so Laravel can get up and running in the first place, but running an artisan command like `php artisan make:auth` will cause Laravel to break. Contributions to this repository attempting to fix this problem will be very welcome.