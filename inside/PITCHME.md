@snap[north]
@size[1.5em](Внутри докера)
@snapend

@snap[west span-50]
@ul[split-screen-list](false)
  - Images - Образы
  - Containers - Контейнеры
  - Registries - Реестры
  - Services - Сервисы
@ulend
@snapend

@snap[east span-50 auto-margin]
![container](images/container.jpg)
@snapend

+++

@snap[north]
@size[1.25em](Images - Образы)
@snapend

@snap[span-80 auto-margin]
![images](images/images.png)
@snapend

+++

@snap[north]
@size[1.25em](Images - Dockerfile)
@snapend

файл с набором инструкций для создания образа будущего контейнера

```
$ docker build -t friendlyhello .
$ docker image ls

REPOSITORY            TAG                 IMAGE ID
friendlyhello         latest              326387cea398
```

+++

@snap[north]
@size[1.25em](Dockerfile)
@snapend

```
FROM ubuntu:latest
MAINTAINER sima
RUN apt-get update
RUN apt-get install nginx
ADD ./nginx.conf /etc/nginx/
EXPOSE 80
CMD [nginx]
```

+++
@snap[north]
@size[1.25em](Dockerfile)
@snapend

Образы в Docker так устроены, что они состоят из нескольких слоев.
Каждая инструкция из Dockerfile создает новый слой образа.

```
$ docker history 00fd29ccc6f1
IMAGE         CREATED       CREATED BY                                      SIZE
00fd29ccc6f1  2 weeks ago   /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>     2 weeks ago   /bin/sh -c mkdir -p /run/systemd && echo '...   7B
<missing>     2 weeks ago   /bin/sh -c sed -i 's, except the top one,/...   2.76kB
<missing>     2 weeks ago   /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>     2 weeks ago   /bin/sh -c set -xe   && echo '#!/bin/sh' >...   745B
<missing>     2 weeks ago   /bin/sh -c #(nop) ADD file:f5a2d04c3f3cafa...   111MB

```
+++

@snap[north]
@size[1.25em](Реестры Docker)
@snapend

библиотека образов

#### Docker Hub

```
$ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
50aff78429b1: Pull complete 
f6d82e297bce: Pull complete 
275abb2c8a6f: Pull complete 
9f15a39356d6: Pull complete 
fc0342a94c89: Pull complete 
Digest: sha256:ec0e4e8bf2c1178e025099eed57c566959bb408c6b478c284c1683bc4298b683
Status: Downloaded newer image for ubuntu:latest
```

+++

@snap[north]
@size[1.25em](Container - Контейнер)
@snapend

запускаемый экземпляр Docker образа

```
$ docker run -p 4000:80 friendlyhello
root@af588b25a4ad:/# 

$ docker container ls
CONTAINER ID        IMAGE               COMMAND             CREATED
1fa4ab2cf395        friendlyhello       "python app.py"     28 seconds ago
```
