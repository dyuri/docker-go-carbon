# Docker image for go-carbon + carbonapi

## Quick Start

```sh
docker run -d\
 --name go-carbon\
 --restart=always\
 -p 8081:8081\
 -p 2003-2004:2003-2004\
 dyuri/go-carbon
```

### Includes the following components

* [Go-carbon](https://github.com/lomik/go-carbon) - Golang implementation of Graphite/Carbon server
* [Carbonapi](https://github.com/go-graphite/carbonapi) - Golang implementation of Graphite-web

### Mapped Ports

Host | Container | Service
---- | --------- | -------------------------------------------------------------------------------------------------------------------
2003 |      2003 | [carbon receiver - plaintext](http://graphite.readthedocs.io/en/latest/feeding-carbon.html#the-plaintext-protocol)
2004 |      2004 | [carbon receiver - pickle](http://graphite.readthedocs.io/en/latest/feeding-carbon.html#the-pickle-protocol)

### Mounted Volumes

Host              | Container                  | Notes
----------------- | -------------------------- | -------------------------------
DOCKER ASSIGNED   | /etc/go-carbon             | go-carbon configs (see )
DOCKER ASSIGNED   | /var/lib/graphite          | graphite file storage
DOCKER ASSIGNED   | /etc/carbonapi             | Carbonapi config
DOCKER ASSIGNED   | /etc/logrotate.d           | logrotate config
DOCKER ASSIGNED   | /var/log                   | log files
