# Deploy server on AWS

## Debian 12

```
sudo apt update
sudo apt install git tmux python3-pip python3-virtualenv libpq-dev net-tools ufw python3-dev libpq-dev nginx curl nmap 
sudo ln -sT /usr/bin/python3 /usr/bin/python
ssh-keygen -t ed25519 -C "your_email@example.com"
```

You may also want:

```
sudo apt install snapd
sudo snap install --classic certbot
```

## Postgresql:

```
sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```
Need to change the permission settings in the file `/etc/postgresql/<version>/main/pg_hba.conf` to allow the connection from the server.

To allow remote connection to database, 3 things need to be done:

1. Change the `listen_addresses` and permission in the file `/etc/postgresql/<version>/main/postgresql.conf` and `/etc/postgresql/<version>/main/pg_hba.conf`.
1. For aws, allow the port 5432 in the security group.
1. On debian, allow port 5432 with `sudo ufw allow 5432`.
