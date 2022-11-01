## Описание проекта

Продуктовый помощник. Смотрите и создавайте рецепты, подписывайтесь на авторов, добавляйте рецепты в избранное и скачивайте список покупок!

## Технологии
Python Django Django REST Framework PostgreSQL Nginx gunicorn docker GitHub%20Actions Yandex.Cloud

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


## Об авторе

Калинин Степан