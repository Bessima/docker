@snap[north]
@size[1.5em](Docker compose)
@snapend

@snap[west span-50]
Пакетный менеджер, позволяющий описывать необходимую структуру в одном файле
@snapend

@snap[east span-50 auto-margin]
![container](images/compose-logo.jpg)
@snapend

+++

@snap[north]
@size[1.25em](docker-compose.yml)
@snapend

docker-compose.yml — это как Dockerfile, но для распределенного приложения целиком

```
version: '2'
services:
    web:
        build: ./web-app
        depends_on: 
        - db
    db:
        image: mysql
        environment:
        - MYSQL_ROOT_PASSWORD=somepassword
```
