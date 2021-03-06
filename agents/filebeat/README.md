# Filebeat

[![Docker image](https://img.shields.io/docker/image-size/astridproject/filebeat?label=image&logo=docker)](https://hub.docker.com/repository/docker/astridproject/filebeat)

## Contents

- [Filebeat](#filebeat)
  - [Contents](#contents)
  - [Installation Steps](#installation-steps)
    - [Setup](#setup)
    - [Requirements](#requirements)
    - [Initialization](#initialization)
    - [Start](#start)
    - [Stop](#stop)
    - [Health](#health)
  - [Docker image](#docker-image)

## Installation Steps

### Setup

The variables are defined in [scripts/vars](scripts/vars).

Name                             | Default value                        | Meaning
---------------------------------|--------------------------------------|--------
COMPONENT                        | filebeat                             | Component name
VERSION                          | 7.8.0                                | Version number
INSTALLATION_PATH                | /opt/`COMPONENT`                     | Directory path where the software will be installed
TMP_PATH                         | /tmp                                 | Temporary dictionary path
SOURCE                           | `$COMPONENT`-`$VERSION`-linux-x86_64 | Source filename
FILE                             | `$SOURCE`.tar.gz                     | Source archive
PIDFILE                          | `$TMP_PATH`/`$COMPONENT`.pid         | File path where the PID of the current execution is stored
ELASTICSEARCH_HOSTS              | localhost:9200                       | Elasticsearch endpoints to connect for monitoring
ELASTICSEARCH_MONITORING_ENABLED | false                                | Enable monitoring with Elasticsearch
LOGSTASH_HOSTS                   | localhost:5044                       | Logstash endpoints where to send the collected data

### Requirements

Enter into the `scripts` directory.

```console
$ cd scripts
```

### Initialization

```console
$ ./init
```

### Start

```console
$ ./start
```

### Stop

```console
$ ./stop
```

### Health

Check if the software is running or not.

```console
$ ./health
```

## Docker image

[Dockerfile](Dockerfile) is used to build the `docker` image with CI in the [https://hub.docker.com/repository/docker/astridproject/filebeat](https://hub.docker.com/repository/docker/astridproject/filebeat).
