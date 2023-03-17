#Linux Version
FROM centos:latest



RUN yum install epel-release  -y
RUN yum update -y

# Install Python

RUN yum install python3 -y



# Install Nginx
RUN yum install nginx1 -y


# set working diretory
WORKDIR /flaskapp


# copy requirements.txt and install
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt


# Copy Flask application code
COPY app.py  app.py
COPY start.sh /start.sh
COPY nginx_config.conf /etc/nginx/conf.d/virtual.conf

EXPOSE 80


RUN chmod +x /start.sh
ENTRYPOINT ["/start.sh"]

