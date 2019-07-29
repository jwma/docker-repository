# Django admin
Just a wrapper which is wrap the official django-admin tools.

## Dockerfile
```
FROM python:3.7-alpine

WORKDIR /djangoadmin
RUN apk update && apk add --no-cache --virtual .setup-deps \
	build-base \
	python3-dev \
	&& pip --no-cache-dir install pipenv \
	&& pipenv install Django==2.2.3 \
	&& pipenv install --system \
	&& apk del --no-cache .setup-deps

CMD ["django-admin"]
```
I use Pipenv in this image, the Pipfile stuff will be store at `/djangoadmin` directory.

## Usage
You can create a new django project like this.
```
docker run --rm -w /app -v $PWD:/app studiomj/django-admin django-admin startproject myproject .
```

If you want to get the Pipfile, Pipfile.lock files, you can run the following command
```
docker run --rm -v $PWD:/app studiomj/django-admin cp /djangoadmin/{Pipfile,Pipfile.lock} /app
```

Or you can create a container first, then use `docker cp` command to copy the files you want.
