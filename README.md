# Project Docker PHP
## by Goodnato

A project template ready to start

- Clone this repo
- Create .env
- Build

## What does the project have?

The following technologies are included:

- [PHP 8.0.2](https://www.php.net/) - New PHP with JIT 😃
- [Composer 2](https://getcomposer.org/) - Composer and PHP together ❤️
- [Xdebug 3](https://xdebug.org/) - Debug your app 🧐
- [Nginx latest](https://www.nginx.com/) - The power HTTP SERVER 😮
- [Redis latest](https://redis.io/) - CACHE CACHE CACHEEEEE 😎
- [Mysql 8](https://www.mysql.com/) - Use index with responsibility 👌
- [Phpmyadmin latest](https://www.phpmyadmin.net/) - Update without where 🎲
- [Node 14.16](https://nodejs.org/en/) - What's the next package? 👀
- [Mailhog latest](https://github.com/mailhog/MailHog) - Test local mails ✉️

# Requirements

> Windows
- [Docker](https://docs.docker.com/engine/install/)

> Linux
- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

First create a .env and set your values

```sh
git clone https://github.com/Goodnato/docker-project-php
cd docker-project-php
cp .env_example .env
nano .env
HTTP_HOST=localhost
HTTP_PORT=80
```

Now BUILD 🙌

```sh
docker-compose up -d --build
Access -> http://localhost
Phpmyadmin -> http://localhost:8080 > username: root, password: 123
```

## Laravel

We all love laravel. So it's easy to install

```sh
rm src/index.php
docker-compose exec php composer create-project laravel/laravel .
docker-compose exec php php artisan
nano .env
change ROOT_PHP for default root laravel -> /var/www/html/public
docker-compose restart
cd src/
nano .env
DB_HOST=mysql
DB_DATABASE=database
DB_USERNAME=user
DB_PASSWORD=123
REDIS_HOST=redis
REDIS_PASSWORD=Redis!
MAIL_HOST=mailhog
MAIL_FROM_ADDRESS=teste@mailhog.local
MAIL_FROM_ADDRESS=Mailhog
access -> http://localhost
```

## NPM

Do you want packages for your application? Great, follow these steps

```sh
cd docker-project-php
docker-compose exec node npm install
docker-compose exec node npm install bootstrap
docker-compose exec node npm install sweetalert2
```

## License

MIT

**Free Software, o/**

v2.1