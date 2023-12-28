# timescale-ubuntu-installation
Timescale Ubuntu Installer<br/><br/>
A Shell Script to Install PostgreSQL 16 & Timescale 2.13 on Ubuntu 22.04<br/><br/>
Upon install you will enter psql terminal, then follow the below steps:<br/><br/>
1) Set the password for the "postgres" user:<br/>
```\password postgres```<br/><br/>

2) Exit from PostgreSQL:<br/>
`\q`<br/><br/>

3) Use "psql" client to connect to PostgreSQL:<br/>
`psql -U postgres -h localhost`<br/><br/>

4) At the "psql" prompt, create an empty database. Our database is called "tsdb":<br/>
`CREATE database tsdb;`<br/><br/>

5) Connect to the database you created:<br/>
`\c tsdb`<br/><br/>

6) Add the TimescaleDB extension:<br/>
`CREATE EXTENSION IF NOT EXISTS timescaledb;`<br/><br/>

```
sudo apt update

sudo apt upgrade

sudo apt install gnupg postgresql-common apt-transport-https lsb-release wget

sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh

sudo echo "deb https://packagecloud.io/timescale/timescaledb/ubuntu/ $(lsb_release -c -s) main" | sudo tee /etc/apt/sources.list.d/timescaledb.list

sudo wget --quiet -O - https://packagecloud.io/timescale/timescaledb/gpgkey | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/timescaledb.gpg

sudo apt update

sudo apt install timescaledb-2-postgresql-16

sudo apt-get update

sudo apt-get install postgresql-client

sudo systemctl restart postgresql

sudo -u postgres psql
```
