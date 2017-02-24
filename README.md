VERDACCIO SERVICE
===============

Script for running [verdaccio](https://github.com/verdaccio/verdaccio) server as daemon

User
----

This script run verdaccio under `verdaccio` user, you should create it

```bash
adduser --no-create-home --disabled-login verdaccio
```

Copy service to init.d

```bash
sudo cp service/verdaccio /etc/init.d/verdaccio
sudo chmod +x /etc/init.d/verdaccio
```

We need also some directories to store configuration and packages

```bash
sudo mkdir /etc/verdaccio
sudo mkdir /etc/verdaccio/storage
sudo mv config.yaml /etc/verdaccio/
sudo chown verdaccio:verdaccio /etc/verdaccio/ -R
sudo chmod g+w /etc/verdaccio/storage
```

You should modify `/etc/verdaccio/config.yaml` for your needs

Start it!

```bash
sudo /etc/init.d/verdaccio start
```

Forked From
-----
Forked from [sinopia-scripts](https://github.com/ramiel/sinopia-scripts) by [Fabrizio "ramiel" Ruggeri](http://www.ramielcreations.com)
