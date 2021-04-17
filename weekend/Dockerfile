FROM centos

RUN yum install httpd -y && \
    yum install git -y

RUN useradd docker_user

ENV app 3-col-portfolio

ENV Documentroot  /var/www

WORKDIR $Documentroot

COPY $app html
#ADD https://github.com/schoolofdevops/html-sample-app /var/www/html


CMD httpd -DFOREGROUND
