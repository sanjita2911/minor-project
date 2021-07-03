FROM ubuntu:20.04

RUN apt-get update -y
RUN apt-get install python3-pip -y
RUN apt-get install gunicorn -y
RUN apt-get install mysql-client -y
RUN apt-get install libmysqlclient-dev -y
RUN apt-get install libssl-dev -y

COPY requirements.txt requirements.txt
COPY minor-project /opt/

RUN pip3 install -r requirements.txt

WORKDIR /opt/

EXPOSE 8000

CMD ["gunicorn","-b","0.0.0.0:8000","app:app","--workers=5"]
