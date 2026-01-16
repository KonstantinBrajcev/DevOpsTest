# Django DevOps Test Project

Проект демонстрирует развертывание Django приложения с использованием Docker, Nginx, PostgreSQL и CI/CD.

## Структура проекта
- `app/` - Django приложение
- `nginx/` - Nginx конфигурация
- `.github/workflows/` - CI/CD конфигурация
- `docker-compose.yml` - для разработки
- `docker-compose.prod.yml` - для продакшена
- `.env.production` - переменные окружения

## Технологии
- Django 4.2
- PostgreSQL 15
- Nginx 1.25
- Docker & Docker Compose
- GitHub Actions CI/CD
- Gunicorn

## Локальный запуск (разработка)
## 🚀 Быстрый старт

1. Клонируйте репозиторий:
```bash
git clone https://github.com/ваш-username/django-devops-test.git
cd django-devops-test
docker-compose up --build

2. Приложение будет доступно:
- Через Nginx (статика + прокси): http://localhost
- Прямо к Django: http://localhost:8000
- PostgreSQL: localhost:5432

## ПРОДАКШЕН ЗАПУСК
## Настройка переменных окружения
cp .env.production.example .env.production

## Запуск
docker-compose -f docker-compose.prod.yml up --build -d

## Структура проекта
django-devops-test/
├── .github/workflows/          # GitHub Actions CI/CD
│   └── ci-cd.yml
├── app/                        # Django приложение
│   ├── Dockerfile
│   ├── entrypoint.sh
│   ├── requirements.txt
│   └── src/
│       ├── manage.py
│       ├── myproject/         # Настройки Django
│       │   ├── settings.py
│       │   ├── urls.py
│       │   └── wsgi.py
│       └── myapp/            # Основное приложение
│           ├── views.py      # "Hello, World!" страница
│           ├── urls.py
│           └── templates/    # HTML шаблоны (создайте если нужно)
│               └── myapp/
│                   └── index.html
├── nginx/                     # Nginx конфигурация
│   ├── Dockerfile
│   └── nginx.conf
├── docker-compose.yml        # Для разработки
├── docker-compose.prod.yml   # Для продакшена
├── .env.production.example   # Пример переменных окружения
└── README.md