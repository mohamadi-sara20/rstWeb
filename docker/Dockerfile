FROM debian
RUN apt-get -yqq update
RUN apt-get install -yqq supervisor apache2 python3-pip
RUN pip install selenium
RUN pip install cherrypy
RUN pip install six>=1.11
RUN a2enmod rewrite
RUN a2enmod cgi
ADD apache-config.conf /etc/apache2/sites-enabled/000-default.conf
ADD supervisord.conf /etc/supervisor/conf.d/
RUN ln -s /usr/bin/python3 /usr/bin/python
CMD ["supervisord"]
