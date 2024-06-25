# Serve PHP Websites Locally using Docker and Apache


docker run -dit --name devopApache -p 8080:80 httpd:2.4
docker run -dit --name devopApache -p 8080:80 -v ${PWD}:/usr/local/apache2/htdocs/ httpd:2.4

create a docker file and add this 2 line -->
FROM httpd:2.4
COPY ./public-html/ /usr/local/apache2/htdocs/

run this command --> to create an image ->
docker build -t appache-img:1.0 .

run this command to create a container --->
docker run -dit --name appcheContainer1 -p 8090:80 appache-img:1.0
