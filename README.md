# Yamdb

![Api Yamdb](https://github.com/Mikhail-Kushnerev/yamdb_final/workflows/yamdb/badge.svg)

Доступен по ссылке:

Документация по сервису:
[Redoc](http://51.250.104.248/redoc/)

## Оглавление

- [Технологии](#технологии)
- [О проекте](#о-проекте)
- [Особенности](#особенности)
- [Развёртывание проекта](#развёртывание-проекта)
- [Авторы](#авторы)

## О проекте

Микросервис **Yamdb**, где пользователи могут оценивать и комментировать книги, фильмы, музыку.

## Технологии

- Python 3.10;
- Django;
- Docker, Docker-Compose;
- PostgreSQL;
- Nginx;
- CI/CD.

## Особенности

Процесс тестирования и деплоя на сервер автоматизировано – телеграмм-бот присылает СМС-уведомление либо о прохождении всех этапов. Проект полностью развернут на [**Docker**](https://hub.docker.com/repository/docker/mikhailkushnerev/yamdb-final), контейнер чей используется на сервере.  
[⬆️Оглавление](#оглавление)

## Развёртывание проекта:

- Слонируйте проект:

```py
git clone https://github.com/Mikhail-Kushnerev/yamdb_final
cd yamdb_final/
```

- Установите виртуальное окружение, активируйте его:

```py
py -m venv env
source env/bin/activate
python3 -m pip install --upgrade pip
```

- Проинсталлируйте необходимые зависимости:

```py
pip install -r requirements.txt
```

- Запустить приложение в контейнерах:

```py
# из директории infra/
docker-compose up -d --build
```

- Выполнить миграции:

```py
# из директории infra/
docker-compose exec web python manage.py migrate
```
- Создать суперпользователя:

```py
# из директории infra/
docker-compose exec web python manage.py createsuperuser
```

- Собрать статику:

```py
# из директории infra/
docker-compose exec web python manage.py collectstatic --no-input
```
- Остановить приложение в контейнерах:

```py
# из директории infra/
docker-compose down -v
```

[⬆️Оглавление](#оглавление)
## Авторы

[Mikhail Kushnerev](https://github.com/Mikhail-Kushnerev)

[В начало](#yamdb)
