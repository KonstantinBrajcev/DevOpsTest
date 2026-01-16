FROM python:3.11-slim

# Устанавливаем системные зависимости
RUN apt-get update && apt-get install -y \
    gcc \
    postgresql-client \
    netcat-openbsd \
    && rm -rf /var/lib/apt/lists/*

# СОЗДАЕМ ПАПКУ staticfiles с правами для всех
RUN mkdir -p /staticfiles && chmod 777 /staticfiles

# Создаем пользователя и его домашнюю директорию
RUN useradd -m -u 1000 django

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем зависимости
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Копируем точку входа
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# Копируем исходный код
COPY src/ .
RUN chown -R django:django /app

USER django

ENTRYPOINT ["/entrypoint.sh"]