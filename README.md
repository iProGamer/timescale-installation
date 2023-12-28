# timescale-installation
## *Ubuntu 22.04*<br/><br/>
A Shell Script to Install PostgreSQL 16 & Timescale 2.13 on Ubuntu 22.04<br/><br/>
1) Run the script<br/>
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
2) Set the password for the "postgres" user:<br/>
`\password postgres`<br/><br/>

3) Exit from PostgreSQL:<br/>
`\q`<br/><br/>

4) Use "psql" client to connect to PostgreSQL:<br/>
`psql -U postgres -h localhost`<br/><br/>

5) At the "psql" prompt, create an empty database. Our database is called "tsdb":<br/>
`CREATE database tsdb;`<br/><br/>

6) Connect to the database you created:<br/>
`\c tsdb`<br/><br/>

7) Add the TimescaleDB extension:<br/>
`CREATE EXTENSION IF NOT EXISTS timescaledb;`<br/><br/>

## *Amazon Linux 2023*<br/><br/>
A Shell Script to Install PostgreSQL 16 & Timescale 2.13 on Ubuntu 22.04<br/><br/>
1) Run the script<br/>
```
sudo yum update
sudo yum upgrade

sudo yum install https://download.postgresql.org/pub/repos/yum/reporpms/F-$(rpm -E %{fedora})-x86_64/pgdg-fedora-repo-latest.noarch.rpm

sudo tee /etc/yum.repos.d/timescale_timescaledb.repo <<EOL
[timescale_timescaledb]
name=timescale_timescaledb
baseurl=https://packagecloud.io/timescale/timescaledb/el/8/$basearch
repo_gpgcheck=1
gpgcheck=0
enabled=1
gpgkey=https://packagecloud.io/timescale/timescaledb/gpgkey
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
metadata_expire=300
EOL

sudo yum update

sudo yum install timescaledb-2-postgresql-16

sudo /usr/pgsql-14/bin/postgresql-14-setup initdb

sudo yum update

sudo dnf install postgresql16

sudo systemctl enable postgresql-16
sudo systemctl start postgresql-16

sudo -u postgres psql
```
2) Set the password for the "postgres" user:<br/>
`\password postgres`<br/><br/>

3) Exit from PostgreSQL:<br/>
`\q`<br/><br/>

4) Use "psql" client to connect to PostgreSQL:<br/>
`psql -U postgres -h localhost`<br/><br/>

5) At the "psql" prompt, create an empty database. Our database is called "tsdb":<br/>
`CREATE database tsdb;`<br/><br/>

6) Connect to the database you created:<br/>
`\c tsdb`<br/><br/>

7) Add the TimescaleDB extension:<br/>
`CREATE EXTENSION IF NOT EXISTS timescaledb;`<br/><br/>
