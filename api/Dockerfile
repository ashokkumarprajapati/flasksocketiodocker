FROM ubuntu:latest
RUN apt-get update
RUN apt-get install python3-pip -y
RUN mkdir /code
WORKDIR /code
ADD requirements.txt .
ADD app.py .
RUN pip3 install -r requirements.txt
RUN echo 'root:password' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN /etc/init.d/ssh restart
CMD ["python3", "app.py"]
EXPOSE 5000
EXPOSE 22
