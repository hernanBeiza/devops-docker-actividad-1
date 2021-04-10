# FROM alpine
# RUN apk add git && apk add nodejs npm
FROM httpd:2.4
# Instalar herramientas necesarias
RUN apt-get update && apt-get install git nodejs npm -y
# Clonar repo
RUN git clone https://github.com/hernanBeiza/devops-calculadora-10-webapp 
# Construir aplicación web
RUN cd devops-calculadora-10-webapp/devops-calculadora-10-webapp && npm install && npm run build
# Copiar configuración del servidor web
COPY ./src/my-httpd.conf /usr/local/apache2/conf/httpd.conf
# Copiar archivos compilados de la webapp a la carpera del servidor web
RUN mv devops-calculadora-10-webapp/devops-calculadora-10-webapp/build/* /usr/local/apache2/htdocs/