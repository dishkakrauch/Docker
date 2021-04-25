FROM apache/airflow:latest

USER root
RUN mkdir -p /usr/src/app/
WORKDIR /usr/src/app/
COPY . /usr/src/app/
RUN apt-get update
RUN apt-get install libsasl2-dev gcc g++ -y

USER airflow
RUN pip3 install --upgrade "apache-airflow[hdfs,azure,hive]==${AIRFLOW_VERSION}" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2).txt"
RUN pip3 install --no-cache-dir -r requirements.txt