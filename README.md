# API YamDB

## Проект Django REST API.

### Описание

- Проект **YaMDb** собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы».

### Запуск проекта

- Клонируем репозиторий и перейдем в него
```python
 docker push ebudaev/yamdb:v1
 git clone https://github.com/EvgeniyBudaev/infra_sp2
 cd infra_sp2/
```

- Установите Docker (https://docs.docker.com/get-started/)

- Запуск приложения

```python
  docker-compose up -d --build
```

- Выполнить миграции и создание суперпользователя

```python
  docker-compose exec web python manage.py makemigrations
  docker-compose exec web python manage.py migrate --noinput
  docker-compose exec web python manage.py createsuperuser
  docker-compose exec web python manage.py collectstatic
```

- Заполнение базы начальными данными

```python
 docker-compose exec web python manage.py loaddata fixtures.json
```

- Остановка приложения

```python
  docker-compose down
```

Инструкция как пользоваться данным API доступна по адресу http://localhost/redoc/