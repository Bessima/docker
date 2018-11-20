@snap[north]
@size[1.5em](Внутри докера)
@snapend

@snap[west span-100]
@ul[split-screen-list](false)
  - Images - Образы
  - Containers - Контейнеры
  - Registries - Реестры
  - Services - Сервисы
@ulend
@snapend

+++

@snap[north]
@size[1.25em](Images - Образы)
@snapend

@snap[span-80 auto-margin]
![logo](images/images.png)
@snapend

+++

@snap[north]
@size[1.25em](Images - Dockerfile)
@snapend

@snap[west span-60 auto-margin]
файл с набором инструкций для создания образа будущего контейнера

```
docker build
```

@snapend

@snap[east span-40 auto-margin]
```

FROM ubuntu:latest
MAINTAINER igor
RUN apt-get update
RUN apt-get install nginx
ADD ./nginx.conf /etc/nginx/
EXPOSE 80
CMD [nginx]

```
@snapend

+++

@snap[north]
@size[1.25em](Платформа docker)
@snapend

@snap[span-50 auto-margin]
![logo](images/container.jpg)
@snapend

+++

@snap[north]
@size[1.25em](Docker Engine)
@snapend

![Docker Engine](images/engine.png)

+++

@snap[north]
@size[1.25em](Архитектура Docker)
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


+++
