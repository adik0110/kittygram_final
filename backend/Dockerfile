FROM python:3.10

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# Создаем директории для статики
RUN mkdir -p /app/collected_static && \
    mkdir -p /backend_static/static

CMD ["sh", "-c", "python manage.py collectstatic --noinput && \
     cp -r /app/collected_static/. /backend_static/static/ && \
     gunicorn --bind 0.0.0.0:8000 kittygram_backend.wsgi"]