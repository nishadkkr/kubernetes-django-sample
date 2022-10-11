FROM ubuntu:22.04
RUN apt-get update && apt-get install -y tzdata && apt install -y python3.10 python3-pip
RUN apt install python3-dev libpq-dev nginx -y
RUN pip install django gunicorn psycopg2
ADD . /app
WORKDIR /app
EXPOSE 8005
CMD ["gunicorn", "--bind", ":8005", "--workers", "3", "myproject.wsgi"]