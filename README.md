### Описание

Проект YaMDb собирает отзывы пользователей на произведения.

Ключевые моменты:

Применены вьюсеты.

Для аутентификации использованы JWT-токены.

У неаутентифицированных пользователей доступ к API только на чтение.


### Установка

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/kirenger/api_yamdb.git
```

```
cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры

Документация API

```
localhost:8000/redoc
```


### Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

### Запуск приложения в контейнерах

Перейти в папку:

```
cd infra/
```

Развернуть контейнеры:

```
docker-compose up
```

Сделать миграции, суперпользователя и собрать статику:

```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```

### Команда для заполнения базы данными


```
sudo docker compose exec web python manage.py loaddata fixtures.json
```
