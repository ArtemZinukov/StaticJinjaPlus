# StaticJinjaPlus Docker

Этот репозиторий содержит Dockerfile для сборки и запуска приложения [StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus). Вы можете использовать Docker для упрощения процесса установки и развертывания приложения.

## Содержание

- [Требования](#требования)
- [Сборка образа](#сборка-образа)
- [Запуск контейнера](#запуск-контейнера)
- [Использование разных версий](#использование-разных-версий)


## Требования

- Установленный [Docker](https://www.docker.com/get-started)
- Учетная запись на [DockerHub](https://hub.docker.com/) (для загрузки образов)

## Сборка образа

Скачать репозиторий с кодом, к себе на компьютер

Для сборки контейнера необходимо выбрать базовый образ ubuntu или python-slim
и перейти в соответствующую папку:

```
cd Dockerfile_python
```
если выбрали образ python-slim и 
```
cd Dockerfile_ubuntu
```
если ubuntu.

Далее соберите Docker образ, используя один из следующих команд:

Для версии 0.1.0:
```
docker build --build-arg VERSION=0.1.0 -t yourusername/staticjinjaplus:0.1.0 .
```
Для версии 0.1.1:
```
docker build --build-arg VERSION=0.1.1 -t yourusername/staticjinjaplus:0.1.1 .
```
Замените yourusername на ваше имя пользователя на DockerHub.

## Запуск контейнера

После успешной сборки образа вы можете запустить контейнер с помощью следующей команды:

```
docker run --rm -it yourusername/staticjinjaplus:0.1.1
```
Замените 0.1.1 на нужную вам версию.

## Использование разных версий

Вы можете собирать и запускать разные версии приложения, передавая соответствующий аргумент VERSION при сборке образа. Например:

Для версии 0.1.0:

```
docker build --build-arg VERSION=0.1.0 -t yourusername/staticjinjaplus:0.1.0 .
docker run --rm -it yourusername/staticjinjaplus:0.1.0
```
Для версии 0.1.1:
```
docker build --build-arg VERSION=0.1.1 -t yourusername/staticjinjaplus:0.1.1 .
docker run --rm -it yourusername/staticjinjaplus:0.1.1
```