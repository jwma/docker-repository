FROM python:3.7-alpine

RUN apk update && apk add --virtual .build-deps \
	build-base \
	libffi-dev \
	gcc \
	python3-dev \
	&& apk add --no-cache postgresql-dev

CMD ["python3"]
