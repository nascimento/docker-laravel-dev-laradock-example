# Laravel development environment using laradock

##  Requirements
- Git
- Docker
- Docker-Compose

##  To run this project

Init laradock as submodule:
```
git submodule update --init --recursive
```

Start development docker:

```
cd laradock && docker-compose up -d nginx mysql redis
```
> (doc laradock)[http://laradock.io/documentation/].

If necessary change permission on storage folder:

```
chmod -R 777 storage/logs
```


##  To start a new project with laradock

Install local php (only necessary to create the project):

[**https://secure.php.net/manual/pt_BR/install.php**](https://secure.php.net/manual/pt_BR/install.php)

Install composer:

[**https://getcomposer.org/doc/00-intro.md**](https://getcomposer.org/doc/00-intro.md)

Install laravel:

```
composer global require "laravel/installer"
```

Create the project:

```
composer create-project --prefer-dist laravel/laravel my_project
```

Init git repository:

```
cd my_project && git init
```

Open your project’s .env file and set the following:

```
DB_HOST=mysql
REDIS_HOST=redis
```

Add laradock as submodule:

```
git submodule add https://github.com/laradock/laradock.git
```

Start development docker:

```
cd laradock
mv env-example .env
docker-compose up -d nginx mysql redis
```

If necessary change permission on storage folder:

```
chmod -R 777 storage/logs
```
