FROM python:3.10-slim-bullseye

RUN mkdir app
RUN mkdir -p /datos/datos_ini

COPY ./main.py /app/
COPY ./client_secrets.json /app/
COPY ./modulos/ /app/modulos/
COPY ./requirements.txt /app/
COPY .env /app/

WORKDIR /app/
RUN apt-get update

#Installing gcc compiler for psycopg2 python library
RUN apt-get install gcc -y 
RUN apt-get install libpq-dev -y

RUN pip install -r requirements.txt


ENTRYPOINT ["python3", "main.py"]
