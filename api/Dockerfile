FROM ubuntu:latest
RUN apt-get update
RUN apt-get install python3-pip -y
RUN mkdir /code
WORKDIR /code
ADD requirements.txt .
ADD app.py .
RUN pip3 install -r requirements.txt
CMD ["python3", "app.py"]
EXPOSE 5000
