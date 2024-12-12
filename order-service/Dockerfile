# Используем базовый образ Python
FROM python:3.8-slim

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файлы приложения в контейнер
COPY . /app

# Устанавливаем зависимости
RUN apt-get update &&\
    apt-get -y install libpq-dev gcc &&\
    pip install --no-cache-dir -r requirements.txt

# Определяем команду для запуска приложения
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "app:app"]
