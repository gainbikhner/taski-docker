# Taski
Приложение для планирования своих задач. Настроен запуск проекта в контейнерах, автоматическое тестирование и деплой на удалённый сервер. Автоматизация настроена с помощью GitHub Actions. При пуше в ветку main: проект тестируется, в случае успешного прохождения тестов образы обновляются на Docker Hub, на сервере запускаются контейнеры из обновлённых образов.

## Автор
Константин Гайнбихнер

## Технологии
- Python 3.9
- Django 3.2.3
- React 18.2.0
- Node.js 18.15.0
- Gunicorn 20.1.0
- Nginx 1.22.1
- Docker 24.0.2

## Установка
1. Склонируйте репозиторий.
```
git clone git@github.com:gainbikhner/taski-docker.git
```
<br>

2. Находясь в головной директории, скомпилируйте проект.
```
docker compose up -d
```
<br>

3. Выполните миграции, соберите статику и скопируйте её в /backend_static/static/.
```
docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r collected_static/. ../backend_static/static/
```
<br>

Сервис доступен по адресу:
```
https://localhost/
```
