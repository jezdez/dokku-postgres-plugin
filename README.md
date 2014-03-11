Postgres plugin for Dokku
-------------------------

Project: https://github.com/progrium/dokku

Installation
------------
```
cd /var/lib/dokku/plugins
git clone https://github.com/jezdez/dokku-postgres-plugin postgres
dokku plugins-install
```

This plugin also requires the dokku-link plugin to be installed:
https://github.com/rlaneve/dokku-link

It uses the excellent PostgreSQL docker image by the people at [Orchard](https://orchardup.com/).

Commands
--------
```
$ dokku help
     postgres:create <app>            Create a Postgres container
     postgres:delete <app>            Delete specified Postgres container
     postgres:info <app>              Display container informations
     postgres:link <app> <container>  Link an app to a Postgres container
     postgres:logs <app>              Display last logs from Postgres contain
```

Simple usage
------------

Create a new Container:
```
$ dokku postgres:create foo            # Server side
$ ssh dokku@server postgres:create foo # Client side

-----> Postgres container created: postgres/foo

       Host: 172.16.0.104
       Private port: 5432
```

Advanced usage
--------------

Deleting containers:
```
dokku postgres:delete foo
```

Linking an app to a specific container:
```
dokku postgres:link foo bar
```

Postgres logs (per container):
```
dokku postgres:logs foo
```

Postgres information:
```
dokku postgres:info foo
```
