FROM mariadb:10.4

ADD scripts/ /docker-entrypoint-initdb.d

ENV MYSQL_ROOT_PASSWORD admin
ENV MYSQL_DATABASE test
ENV MYSQL_USER admin
ENV MYSQL_PASSWORD admin

#RUN apt-get update && apt-get -y install vim

EXPOSE 3306

CMD ["mysqld"]