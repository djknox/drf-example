# drf-example

drf-example is a project created to learn how to build applications using [Django Rest Framework](https://www.django-rest-framework.org/).

drf-example is built on [Django](https://www.djangoproject.com/), with [Django Rest Framework](https://www.django-rest-framework.org/) for creating a RESTful API and [django-rest-auth](https://django-rest-auth.readthedocs.io/en/latest/index.html) for token-based authentication.

The project is currently a blog in which Posts can be added, deleted, updated, etc. through HTTP requests.

Dockerfile and docker-compose.yml files are included to allow for development using a [Docker](https://docs.docker.com/develop/) container.


## Setting Up the Dev Environment

Ensure that [Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/) is installed. This will also install [Docker Compose](https://docs.docker.com/compose/), which is used for defining and running Docker apps using the Dockerfile and docker-compose.yml files.

After cloning this repository;
```bash
git clone https://github.com/djknox/drf-example.git
```

Build the image and run the container with Docker Compose:
```bash
docker-compose up --build
```
This will set up a PostgreSQL database at port 5432 (as defined in settings.py) and serve the Django app at port 8000 (as defined in docker-compose.yml).

The container can be stopped and removed with:
```bash
docker-compose down
```

## Installing New Packages

New dependencies should be installed within Docker using [pipenv](https://pipenv-fork.readthedocs.io/en/latest/). For example, to install Django REST Framework:
```bash
docker-compose run web pipenv install djangorestframework
```

The container should then be stopped and the image re-built;
```bash
docker-compose down
docker-compose up --build
```