## Описание проекта

Продуктовый помощник. Смотрите и создавайте рецепты, подписывайтесь на авторов, добавляйте рецепты в избранное и скачивайте список покупок!

## Технологии

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)

#### Установка на удаленный сервер Docker  

Установка утилиты для скачивания файлов
```
sudo apt install curl
```

Эта команда скачает скрипт для установки докера 
```
curl -fsSL https://get.docker.com -o get-docker.sh
``` 

Эта команда запустит его
```
sh get-docker.sh 
``` 

#### Установка на удаленный сервер Docker Compose 
```
sudo apt install docker-ce docker-compose -y 
```
#### Клонирование проекта

Сперва клонируйте репозиторий на локальную машину

```
git clone git@github.com:Stepan3006/foodgram-project-react.git
cd foodgram-project-react/infra
```

#### Создание .env-файла

На production обязательно заменить значение SECRET_KEY

С помощью команды ниже в папке будет создан .env-файл

```
echo 'SECRET_KEY=super-secret
ALLOWED_HOSTS=*
DEBUG=0
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
' > .env
```

#### Сборка контейенеров

Соберите контейнеры и запустите их

```
docker compose up -d
docker compose exec backend python manage.py createsuperuser
```

### Заполнение базы данных

Заполните БД подготовленными данными при первом запуске

```
sudo docker-compose exec backend python manage.py importingredients --path 'recipes/data/ingredients.json'
sudo docker-compose exec backend python manage.py importingredients --path 'recipes/data/tags.json'

```
### Работающий проект 

http://158.160.17.0/

## Об авторе

Калинин Степан