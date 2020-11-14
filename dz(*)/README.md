#### Стенд для занития с Docker.

Цель:

1. Создайть кастомные образы nginx и php, объедините их в docker-compose. После запуска nginx должен показывать php info.

Создадим два новый образ, из Dockerfile
```
# docker build -t konstantinzubarev/my-nginx:v1.1 .
```
```
# docker build -t konstantinzubarev/my-php:v1.1 .
```

Проверим, выведим список всех образов на хост машине.

```
# docker images

REPOSITORY                   TAG                 IMAGE ID            CREATED             SIZE
konstantinzubarev/my-php     v1.1                5ddaae937e5c        6 seconds ago       33MB
konstantinzubarev/my-nginx   v1.1                9405799c923a        28 seconds ago      8.77MB
alpine                         3.12                d6e46aa2470d        3 weeks ago         5.57MB

```

Загрузим наши образы на `Docker Hub`

```
# docker push konstantinzubarev/my-nginx:v1.1
```
Ссылка на Docker Hub: <https://hub.docker.com/repository/docker/konstantinzubarev/my-nginx>
```
# docker push konstantinzubarev/my-php:v1.1
```
Ссылка на Docker Hub: <https://hub.docker.com/repository/docker/konstantinzubarev/my-php>


Для проверки ДЗ, выполним 
```
# docker-compose up -d
```

Передти в браузер на следующие страницы `localhost/index.html`, `localhost/index.php`

Ссылка на дополнительную информацию
- [Alpine + PHP](https://wiki.alpinelinux.org/wiki/Nginx_with_PHP)
