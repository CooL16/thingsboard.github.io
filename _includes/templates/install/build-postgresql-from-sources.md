```bash
# Download sources of postgresql 
wget https://ftp.postgresql.org/pub/source/v12.0/postgresql-12.0.tar.bz2

# Unzip them
tar xvf postgresql-12.0.tar.bz2

# Enter the folder with sources
cd postgresql-12.0/

# The first step of the installation procedure is to configure the source tree for your system
./configure --prefix=/var/lib/postgresql

# Build everything
make world
sudo make install-world

```
{: .copy-code}
Once PostgreSQL is installed you may want to create a new user or set the password for the the main user. The instructions below will help to set the password for main postgresql user
```bash
cd /var/lib/postgresql

sudo chown -R your_username. ../postgresql/

export PGDATA=/var/lib/postgresql/main

# Initialize DB
./bin/pg_ctl initdb

# Start PostgreSQL
./bin/pg_ctl -D /var/lib/postgresql/main/ start

# Enter psql
./bin/psql -h localhost -U your_username postgres

\password
create database thingsboard;
\q
```
{: .copy-code}