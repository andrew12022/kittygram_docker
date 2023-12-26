# Kittygram

**Kittygram** — социальная сеть для обмена фотографиями любимых питомцев. Это полностью рабочий проект, который состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

## Функции
- Kittygram даёт возможность пользователям поделиться и похвастаться фотографиями своих любимых котиков.
- Зарегистрированные пользователи могут создавать, просматривать, редактировать и удалять свои записи.

## Установка

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:andrew12022/kittygram_final.git
```

```
cd kittygram_final/backend
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Создать файл `.env` в исходной папке проекта:

```.env
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
SECRET_KEY='указать секретный ключ'
DEBUG='указать режим работы(False или True)'
ALLOWED_HOSTS='указать внешний IP сервера, 127.0.0.1, localhost, домен(через запятые, без пробелов)'
```

Выполнить миграции:

```
python manage.py migrate
```

### Контейнеризация

Развернуть контейнеры при помощи docker-compose.production.yml:
```
docker compose -f docker-compose.production.yml up
```

Выполнить миграции:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```

Собрать статику:
```
docker compose -f docker-compose.production.yml exec backend python manage.py collecstatic
```

Скопировать статику
```
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
```

## Технологии и необходимые инструменты
- Python 3.9
- Django 3.2.16
- PostgreSQL
- Docker
- Node.js 9.x.x
- Nginx
- Gunicorn 20.x.x
- React 
- python-dotenv
- DRF

## Автор
- [Андрей Елистратов](https://github.com/andrew12022)
