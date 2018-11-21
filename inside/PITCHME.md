@snap[north]
@size[1.5em](Внутри докера)
@snapend

@snap[west span-50]
@ul[split-screen-list](false)
  - Images - Образы
  - Registries - Реестры
  - Containers - Контейнеры
@ulend
@snapend

@snap[east span-50 auto-margin]
![container](images/container.jpg)
@snapend

+++

@snap[north]
@size[1.25em](Images - Образы)
@snapend


@snap[west span-20 auto-margin]
шаблон формата "только для чтения" с инструкциями для создания контейнера
@snapend

@snap[east span-80 auto-margin]
![images](images/images.png)
@snapend

+++

@snap[north]
@size[1.25em](Images - Dockerfile)
@snapend

набор инструкций для создания образа будущего контейнера

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

Каждый dockerfile начинается  указания основного образа

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

@snap[west span-50]
Образы в Docker так устроены, что они состоят из нескольких слоев.

Union FS позволяет объединить слои в единый образ.
@snapend

@snap[east span-50 auto-margin]
![container](images/sharing-layers.jpg)
@snapend

+++

Каждая инструкция из Dockerfile создает новый слой образа.

```
FROM ubuntu:latest
MAINTAINER sima
RUN apt-get update
RUN apt-get install nginx
ADD ./nginx.conf /etc/nginx/
EXPOSE 80
CMD [nginx]
```

```
$ docker history 00fd29ccc6f1
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
  @size[1.1em](Container - Контейнер)
@snapend

@snap[west span-50]
  запускаемый экземпляр Docker образа / процесс
@snapend

@snap[east span-50 auto-margin]
@ul[split-screen-list](false)
  - дополнительные файлы, добавленные в результате создания
  - метеданные
  - основное содержимое, определяемое образом
@ulend
@snapend

+++

@snap[north]
  @size[1.1em](Container - Контейнер)
@snapend

```
$ docker run -p 4000:80 friendlyhello
root@af588b25a4ad:/# 

$ docker container ls
CONTAINER ID        IMAGE               COMMAND             CREATED
1fa4ab2cf395        friendlyhello       "python app.py"     28 seconds ago
```
+++

@snap[north]
@size[1.25em](Docker Engine)
@snapend

![Docker Engine](images/engine.png)

+++

@snap[north]
@size[1.25em](Docker Engine)
@snapend

![Docker Architecture](images/architecture.png)

+++

@snap[north]
@size[1.25em](Причины популярности)
@snapend

@snap[west span-100]
@ul[split-screen-list](false)
  - Гибкость и простота распростронения
  - Простота и компактность
  - Легкость внесения обновлений и изменений
  - Масштабируемость
@ulend
@snapend
