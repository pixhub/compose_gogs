# compose_gogs
docker-compose Gogs and Percona-MySQL server behind Trafik

# What it provides

This docker-compose.yml builds a Gogs server with Git and his MySQL Database behind a Traefik reverse Proxy.
The Traefik reverse Proxy is in a DMZ Network,
Gogs server is in the Backoffice Network,
MySQL Percona Database in the Backoffice Network.

All the applicative Chain communicates through Traefik.

## Test it on local

### Requirements

If you want to test it in local, first add the following in your `/etc/hosts` file :
```
127.0.0.1 traefik.domain.local gogs.domain.local
```

### Here we go

Now go into your home directory :
```
cd /home/$USER
```

Download the compose_gogs repository :
```
git clone https://github.com/pixhub/compose_gogs
```

Go into the repo and lauch the compose file :
```
cd compose_gogs/gogs
docker-compose up -d
```

## Tests

Just wait one minute for Database initialisation, and open your favorite Web Browser to go to :
```
http://gogs.domain.local
```

To configure the Database, just put `mysql_db` in the right gogs installation field, that's the container's name I inquired in the docker-compose file

Also, you can access to the Traefik Dashboard by :
```
http://traefik.domain.local
```

Best regards,
pixhub.
