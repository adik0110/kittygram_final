## Kittygram: Краткое описание проекта

## Функциональность:

- Регистрация/Авторизация
- Добавление, редактирование, удаление информации о котах (имя, год рождения, фото, достижения)
- Панель администратора

## Технологии:

- Backend: Python Django (Django, DRF, Djoser, Gunicorn, Psycopg2, Pillow)
- Frontend: JavaScript React

 ## Развертывание:
docker compose up --build -d
docker container exec kittygram_final-backend-1 python manage.py migrate


Необходимо настроить .env файл
```dotenv
POSTGRES_USER=
POSTGRES_PASSWORD=
POSTGRES_DB=

DB_HOST=db
DB_PORT=5432

SECRET_KEY=
ALLOWED_HOSTS=
```

# Как протестировать

## Задача:

Настроить запуск Kittygram в контейнерах и CI/CD с использованием GitHub Actions.

## Проверка:

1.  Создать tests.yml в корне проекта с данными о домене и Docker Hub.
2.  Скопировать .github/workflows/main.yml в kittygram_workflow.yml в корне проекта.
3.  Локальный запуск тестов: python -m venv venv && source venv/bin/activate (Linux/macOS) или python -m venv venv && venv\Scripts\activate (Windows), pip install -r backend/requirements.txt, pytest в корне проекта.

## Чек-лист перед отправкой:

- Проект Kittygram доступен по доменному имени, указанному в tests.yml.
- Пуш в main запускает тестирование и деплой Kittygram с уведомлением в Telegram.
- В корне проекта есть файл kittygram_workflow.yml.