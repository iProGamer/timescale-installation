# timescale-ubuntu-installation
A shell script to install Postgres + Timescale on Ubuntu

sudo apt install gnupg postgresql-common apt-transport-https lsb-release wget<br /><br />
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh<br />
sudo echo "deb https://packagecloud.io/timescale/timescaledb/ubuntu/ $(lsb_release -c -s) main" | sudo tee /etc/apt/sources.list.d/timescaledb.list<br />
sudo wget --quiet -O - https://packagecloud.io/timescale/timescaledb/gpgkey | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/timescaledb.gpg<br />
sudo apt update<br />
sudo apt install timescaledb-2-postgresql-16<br />
sudo apt-get update<br />
sudo apt-get install postgresql-client<br />
