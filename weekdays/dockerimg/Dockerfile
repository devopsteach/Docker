FROM centos

RUN yum -y install \
	httpd \
	git \
	unzip

#COPY htmlapp /var/www/html


ENV DocumentRoot /var/www/html 

ENV app project-website-template

WORKDIR $DocumentRoot

RUN echo "testing WORKDIR" > workdir.html

ADD https://github.com/yenchiah/$app/archive/refs/heads/master.zip /tmp/htmlapp.zip

RUN unzip  /tmp/htmlapp.zip -d $DocumentRoot && \
    mv $DocumentRoot/$app-master/* $DocumentRoot && \
    rm -rf $DocumentRoot/$app-master && \
    echo "$app, $DocumentRoot" > $DocumentRoot/doc.html

RUN useradd rajesh && \
    chmod 777 $DocumentRoot 

USER rajesh

RUN whoami > user.html

USER root

CMD httpd -DFOREGROUND
