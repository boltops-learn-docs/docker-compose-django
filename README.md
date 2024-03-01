<!-- note marker start -->
NOTE: This repo contains only the documentation for the private BoltsOps repo code.
Original file: https://github.com/boltops-learn/docker-compose-django/blob/master/README.md
The docs are publish so they are available for interested subscribers.
For access to the source code, you can become a BoltOps subscriber.
See: https://learn.boltops.com

<!-- note marker end -->

# Docker Compose Django Example Tutorial

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

This tutorial shows you how to set up docker compose with Django.

Walks you through the process from a brand new Django app to the docker-compose.yml.

Setting this up so development works with both local and docker setup. Found this to be more useful.

## Docker Compose Commands

    docker-compose build
    docker-compose up
    docker-compose exec web

More:

    docker-compose start
    docker-compose stop

## Docker Commands

    docker build -t boltops/docker-compose-django .
    docker run boltops/docker-compose-django
    docker push boltops/docker-compose-django

## Notes

Replace boltops with your own DockerHub username if you are going through the tutorial.

## Python Commands Summary

Build Project

    django-admin startproject mysite
    vim requirements.txt
    pip install -r requirements.txt
    vim mysite/settings.py # change db, dont forget import os
    python manage.py runserver
    mysql -uroot -e 'create database mysite_development'
    python manage.py migrate

Add polls app

    python manage.py startapp polls
    vim polls/models.py
    vim polls/urls.py
    vim mysite/settings.py # install app
    python manage.py makemigrations polls
    python manage.py sqlmigrate polls 0001
    python manage.py migrate
    python manage.py shell

Shell Testing

```python
from polls.models import Choice, Question
Question.objects.all()
Question.objects.all().count()
```

Create admin user

    python manage.py createsuperuser

## Video

[![Watch the video](https://uploads-learn.boltops.com/nsrymvgpeo5f3aap3q1t1rfceaps)](https://learn.boltops.com/courses/docker/lessons/docker-compose-with-django)

Note: Premium video content requires a subscription.