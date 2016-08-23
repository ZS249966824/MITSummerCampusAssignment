FROM zs249966824/ubuntu_java:latest

RUN apt-get update -y
RUN apt-get install -y python-pip python-dev build-essential
RUN pip install watson-developer-cloud
RUN pip install cassandra-driver
COPY . /app
WORKDIR /
RUN pip install -r app/requirements.txt
RUN mkdir spark-2.0.0-bin-hadoop2.7
COPY spark-2.0.0-bin-hadoop2.7 /spark-2.0.0-bin-hadoop2.7
ENTRYPOINT ["/spark-2.0.0-bin-hadoop2.7/bin/spark-submit"]
CMD ["/app/app.py"]
