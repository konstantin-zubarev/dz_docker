#### Стенд для занития с Docker.

Цель:

1. Создайть свой кастомный образ nginx на базе alpine. После запуска nginx должен отдавать кастомную страницу (достаточно изменить дефолтную страницу nginx)

Создадим новый образ, из Dockerfile
```
# docker build -t konstantinzubarev/my-nginx:v1.0 .
```
Проверим, выведим список всех образов на хост машине.

```
# docker images

REPOSITORY                   TAG                 IMAGE ID            CREATED             SIZE
konstantinzubarev/my-nginx   v1.0                965a584134f4        5 minutes ago       8.83MB
alpine                       3.12                d6e46aa2470d        3 weeks ago         5.57MB

```

Запустим созданный образ `konstantinzubarev/my-nginx` в фоновом режиме с именем `my-nginx`
```
# docker run -d -p 80:80 --name my-nginx konstantinzubarev/my-nginx:v1.0
```

Проверим, состояние нашего контенера
```
# docker ps
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS              PORTS                NAMES
a80f421cbf60        konstantinzubarev/my-nginx:v1.0   "nginx -g 'daemon of…"   8 seconds ago       Up 8 seconds        0.0.0.0:80->80/tcp   my-nginx
```

Откром браузер и ведем адрес `localhost` должна открыться наша страница.

Загрузим наш образ на `Docker Hub`

```
# docker push konstantinzubarev/my-nginx:v1.0
```
Ссылка на Docker Hub: <https://hub.docker.com/repository/docker/konstantinzubarev/my-nginx>

Для проверки ДЗ, выполним

```
# docker run -d -p 80:80 --name my-nginx konstantinzubarev/my-nginx:v1.0
```
Передти в браузер на следующие страницы `localhost`

###Вопросы###
1. Определите разницу между контейнером и образом?
2. Можно ли в контейнере собрать ядро?

###Ответы###
1. Образ - это метаинформация, а контейнер - это образ который запущен/остановлен.
2. В контейнере собрать ядро, можно, из программы и исходников.

Ссылка на дополнительную информацию
- [Alpine + Nginx](https://wiki.alpinelinux.org/wiki/Nginx)
