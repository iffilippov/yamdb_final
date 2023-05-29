![<-yamdb workflow](https://github.com/iffilippov/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Проект «API для YaMDb»

### Описание:

Проект YaMDb собирает отзывы пользователей на произведения.

Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Список категорий может быть расширен.
Произведению может быть присвоен жанр из списка предустановленных (например, «Сказка», «Рок» или «Артхаус»).
Добавлять произведения, категории и жанры может только администратор.

Пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку; из пользовательских оценок формируется рейтинг произведения.
Пользователи могут оставлять комментарии к отзывам.
Добавлять отзывы, комментарии и ставить оценки могут только аутентифицированные пользователи.

### Зона ответственности в проекте:

Работа с пользователями. Реализованы:  

* Модель пользователя. Система регистрации и аутентификации;
* Настройка прав доступа;
* Работа с токеном;
* Система подтверждения через E-mail.

### Технологии:

[![Python](https://img.shields.io/badge/-Python-464641?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![DjangoREST](https://img.shields.io/badge/Django-REST-464646?style=flat-square&logo=django&logoColor=white&color=ff1709&labelColor=gray)](https://www.django-rest-framework.org/)
[![Postgres](https://img.shields.io/badge/Postgres-464646?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![Pytest](https://img.shields.io/badge/-Pytest-464646?style=flat-square&logo=pytest)](https://docs.pytest.org/en/6.2.x/)

### Запуск проекта:

Убедиться что установлен Docker:
```bash
docker -v
```
Проверить, что установлена последняя версия [Docker Compose](https://docs.docker.com/compose/install/).

Также можно воспользоваться официальной [инструкцией](https://docs.docker.com/engine/install/).


Клонировать репозиторий и перейти в него:
```bash
git clone https://github.com/iffilippov/infra_sp2
cd infra_sp2/api_yamdb
```

Перейти в папку с docker-compose.yaml:
```bash
cd infra
```

Запустить `docker-compose`
   ```bash
   docker-compose up -d
   ```


Выполнить миграции:
```bash
docker-compose exec web python manage.py makemigrations
```
```bash
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:
```bash
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:
```bash
docker-compose exec web python manage.py collectstatic --no-input
```

Заполнить базу тестовыми данными данными:
```bash
docker-compose exec web python manage.py csv_import
```

Документация доступна по адресу:

```
http://localhost/redoc/
```

### Авторы:
[Эдуард Соловьев](https://github.com/Guten-Edd)

[Елена Посохова](https://github.com/Elenka-Posohova)

[Иван Филиппов](https://www.linkedin.com/in/iffilippov/)

<img src="https://github.com/blackcater/blackcater/raw/main/images/Hi.gif" width="50" height="50"/>
