FROM mrlnx/ubuntu-base

MAINTAINER "Marlon A.H. Lede" <marlonlede@gmail.com>

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main" > /etc/apt/sources.list.d/pgdg.list

# Update
RUN apt-get update

# Install postgress
RUN apt-get install -y -q postgresql-9.5 postgresql-client-9.5 postgresql-contrib-9.5 
RUN /etc/init.d/postgresql stop

# Add listen address to 
USER root
RUN echo "listen_addresses='*'" >> /etc/postgresql/9.5/main/postgresql.conf
RUN echo "host all  all    0.0.0.0/0  md5" >> /etc/postgresql/9.5/main/pg_hba.conf

# Expose to postgres port
EXPOSE 5432

# Switch to user to setup
USER postgres

RUN /etc/init.d/postgresql start && su postgres -c "psql --command \"ALTER USER pguser WITH password 'pguser';\" "
RUN createdb -O pguser pgdb

RUN mkdir -p /var/run/postgresql && chown -R postgres /var/run/postgresql

# Add volumes to allow backup config, logs and databases
VOLUME  ["/etc/postgresql", "/var/log/postgresql", "/var/lib/postgresql"]

USER postgres

# Set the default command to run when starting the container
CMD ["/usr/lib/postgresql/9.5/bin/postgres", "-D", "/var/lib/postgresql/9.5/main", "-c", "config_file=/etc/postgresql/9.5/main/postgresql.conf"]
