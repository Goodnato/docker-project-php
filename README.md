# Project Docker
## by Goodnato

A project template ready to start

- Clone this repo
- Create .env
- Build

## What does the project have?

The following technologies are included:

- [PHP 8.0.2](https://www.php.net/) - New PHP with JIT 😃
- [Composer 2](https://getcomposer.org/) - Composer and PHP together ❤️
- [Nginx latest](https://www.nginx.com/) - The power HTTP SERVER 😮
- [Redis latest](https://redis.io/) - CACHE CACHE CACHEEEEE 😎
- [Mysql 8](https://www.mysql.com/) - Use index with responsibility 👌
- [Node 14.16](https://nodejs.org/en/) - What's the next package? 👀

## Installation

Fist create a .env and set your values

```sh
cd <your-project>
cp .env_example .env
nano .env
HTTP_HOST=localhost
```

Now BUILD 🙌

```sh
docker-compose up -d --build
access -> http://localhost
```

## Laravel

We all love laravel. So it's easy to install

```sh
rm src/index.php
docker-compose exec php composer create-project laravel/laravel .
docker-compose exec php php artisan
cd src/
nano .env
DB_HOST=mysql
REDIS_HOST=redis
```

## NPM

Do you want packages for your application? Great, follow these steps

```sh
cd <your-project>
docker-compose exec node npm install
docker-compose exec node npm install sweetalert2
```

## License

MIT

**Free Software, Hell Yeah!**