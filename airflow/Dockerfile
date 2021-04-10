FROM apache/airflow:latest

USER root
RUN mkdir -p /usr/src/app/
WORKDIR /usr/src/app/
COPY . /usr/src/app/

USER airflow
RUN pip3 install apache-airflow --no-cache-dir -r requirements.txt