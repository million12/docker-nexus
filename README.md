# docker-nexus
[![CircleCI Build Status](https://img.shields.io/circleci/project/million12/docker-nexus/master.svg)](https://circleci.com/gh/millio12/docker-nexus)
[![GitHub Open Issues](https://img.shields.io/github/issues/million12/docker-nexus.svg)](https://github.com/million12/docker-nexus)
[![GitHub Stars](https://img.shields.io/github/stars/million12/docker-nexus.svg)](https://github.com/million12/docker-nexus)
[![GitHub Forks](https://img.shields.io/github/forks/million12/docker-nexus.svg)](https://github.com/million12/docker-nexus)  
[![Stars on Docker Hub](https://img.shields.io/docker/stars/million12/nexus.svg)](https://hub.docker.com/r/million12/nexus)
[![Pulls on Docker Hub](https://img.shields.io/docker/pulls/million12/nexus.svg)](https://hub.docker.com/r/million12/nexus)  
[![Docker Layers](https://badge.imagelayers.io/million12/nexus:latest.svg)](https://hub.docker.com/r/million12/nexus)


[Dockr Image](https://hub.docker.com/r/million12/nexus) with [Nexus](http://www.sonatype.com/nexus/solution-overview) build on top of official [CentOS-7](https://hub.docker.com/_/centos/) image.

### Build
Too build just type:  

    docker build -t million12/nexus .  

### Run
Too run container:  

    docker run \
    --name nexus \
    -p 8081:8081 \
    million12/nexus

### Access web-interface


|*Tool* | *Link* | *Credentials* |
| ------------- | ------------- | ------------- |
| Nexus | http://${docker-machine ip default}:8081/nexus | admin/admin123 |

### Docker troubleshooting


Use docker command to see if all required containers are up and running:

    $ docker ps -a

Check online logs of nexus container:

    $ docker logs nexus

Attach to running nexus container (to detach the tty without exiting the shell,
use the escape sequence Ctrl+p + Ctrl+q):

    $ docker attach nexus

Sometimes you might just want to review how things are deployed inside a running container, you can do this by executing a _bash shell_ through _docker's exec_ command:

    docker exec -i -t nexus /bin/bash

History of an image and size of layers:

    docker history --no-trunc=true million12/nexus | tr -s ' ' | tail -n+2 | awk -F " ago " '{print $2}'

---
## Author

Author: Przemyslaw Ozgo [linux@ozgo.info](mailto:linux@ozgo.info)

Licensed under: The MIT License (MIT)

**Sponsored by** [PrototypeBrewery.io - the new prototyping tool](http://prototypebrewery.io/)
for building fully interactive prototypes of your website or web app. Built on top of
Neos CMS and Zurb Foundation framework.