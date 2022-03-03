FROM python:alpine3.15
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
WORKDIR /app
ADD ./requirements.txt requirements.txt
RUN apk add --update --no-cache curl g++ gcc libxslt-dev && pip install psycopg2-binary && pip install -r requirements.txt
ADD . .
USER 1001
CMD python manage.py migrate && python manage.py runserver 0.0.0.0:8000