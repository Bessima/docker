@snap[north]
@size[1.5em](Docker)
@snapend

@snap[span-100]
![logo](images/Intro-to-Docker.png)
@snapend

+++

@snap[span-100]
![logo](images/ship.jpg)
@snapend

+++

@snap[span-100]
![logo](images/ship2.jpg)
@snapend

+++

@snap[north]
@size[1.5em](Docker)
@snapend

@snap[span-100]
Инструмент для упрощения создания, развертывания и запуска приложений с использованием контейнеров.
@snapend

@snap[south-east span-20]
![logo](images/docker-whales.png)
@snapend

+++

@snap[north]
@size[1.25em](Основные термины)
@snapend


@snap[west span-100]
@ul[split-screen-list](false)
  - Image: собранная подсистема
  - Container: процесс, инициализированный на базе образа
  - Host: среда, в которой запускается докер
  - Volume: дисковое пространство между хостом и контейнером.
@ulend
@snapend

+++

@snap[north]
@size[1.25em](Linux - контейнеры)
@snapend

@snap[west span-50 auto-margin]
![logo](images/linux-container.png)
@snapend

@snap[east span-50 auto-margin]
![logo](images/containers.png)
@snapend

+++

@snap[north]
@size[1.25em](Базовые технологии)
@snapend

@snap[span-100 auto-margin]
@ul[split-screen-list](false)
  - Namespaces - пространства имен
  - Control groups - группы управления
  - UnionFS
@ulend
@snapend

+++

@snap[north]
@size[1.25em](Namespaces)
@snapend

@snap[west span-50 auto-margin]
Пространства имен - изолированное рабочее пространство для контейнера
@snapend

@snap[east span-50 auto-margin]
@ul[split-screen-list](false)
  - PID - Изоляция процесса
  - Net - Управление сетевми интерфейсами
  - MNT - управление точками монтирования
  - ....
@ulend
@snapend

+++

@snap[north]
@size[1.25em](Control groups)
@snapend

@snap[west span-100 auto-margin]
Группы управления - управление ресурсами для процесса: разделение аппаратных ресурсов между контейнерами и применение наложения ограничений при необходимости
@snapend

+++

@snap[north]
@size[1.25em](Файловая система UnionFS)
@snapend

@snap[west span-100 auto-margin]
работает путем создания слоев, делая их легковестными и быстрыми.
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
