FROM centos

RUN yum -y install \
	httpd \
	git \
	unzip

#COPY htmlapp /var/www/html

ENV DocumentRoot /var/www/html 
ENV app project-website-template

ADD https://github.com/yenchiah/$app/archive/refs/heads/master.zip /tmp/htmlapp.zip

RUN unzip  /tmp/htmlapp.zip -d $DocumentRoot && \
    mv $DocumentRoot/project-website-template-master/* $DocumentRoot && \
    rm -rf $DocumentRoot/project-website-template-master && \
    echo "$app, $DocumentRoot" > $DocumentRoot/doc.html


CMD httpd -DFOREGROUND
