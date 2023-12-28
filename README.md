# timescale-ubuntu-installation
A Shell Script to Install PostgreSQL 16 & Timescale 2.13 on Ubuntu 22.04

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
