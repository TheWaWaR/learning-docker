FROM centos:centos7
MAINTAINER weet <thewawar@gmail.com>

RUN yum install -y http://yum.postgresql.org/9.3/redhat/rhel-6-x86_64/pgdg-redhat93-9.3-1.noarch.rpm
RUN yum install -y postgresql93-server postgresql93-contrib

RUN /usr/pgsql-9.3/bin/postgresql93-setup initdb
RUN echo "host all  all    0.0.0.0/0  md5" >> /var/lib/pgsql/9.3/data/pg_hba.conf
RUN echo "listen_addresses='*'" >> /var/lib/pgsql/9.3/data/postgresql.conf

USER postgres
RUN /usr/pgsql-9.3/bin/pg_ctl start -D /var/lib/pgsql/9.3/data -s -w && psql --command "CREATE USER docker WITH SUPERUSER PASSWORD 'docker';" && /usr/pgsql-9.3/bin/pg_ctl stop -D /var/lib/pgsql/9.3/data -s -w

EXPOSE 5432
ENTRYPOINT ["/usr/pgsql-9.3/bin/postgres", "-D", "/var/lib/pgsql/9.3/data"]