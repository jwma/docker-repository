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
