Easy Laravel
==========

Get Laravel up and running from the terminal as quickly and easily as possible. Made for Mac.

## Software
- Nginx
- Mariadb (MySQL)
- Redis

## Requirements
- [Docker](https://docs.docker.com/engine/installation/) (including docker-compose)
- [Composer](https://getcomposer.org/download/) cli (not composer.phar)
- Approx. 600MB storage

## Installation
    $ git clone https://github.com/wilkesreid/easy-laravel laravel
    $ cd laravel
    $ ./install
- Visit localhost in your browser.

## Instructions

The `code` folder contains the Laravel files.

Typing `./artisan` will allow you to execute artisan commands inside the php container. Trying to `cd code` and then `php artisan` will cause issues, especially when trying to do things related to the database or cache. E.g. `./artisan migrate`; `./artisan cache:clear`

Modify `site.conf` to change the nginx configuration, and then run `./reset` to apply the changes.

Modify `php.ini` to change the php configuration, and then run `./reset` to apply the changes.

`./reset` resets nginx and php.

Type `./web_shell` to use the terminal inside the nginx container.

Type `./php_shell` to use the terminal inside the php container.

## Removing

    $ ./uninstall
    
This command will permanently remove everything from your system that was created from the `./install` command.

To stop Laravel without permanently deleting it, run `docker-compose down`.

## Major Issues

- [#2](https://github.com/wilkesreid/easy-laravel/issues/2)