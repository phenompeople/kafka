[![Docker Automated build](https://img.shields.io/docker/automated/phenompeople/kafka.svg?style=plastic)](https://hub.docker.com/r/phenompeople/kafka/)
[![Docker Build Status](https://img.shields.io/docker/build/phenompeople/kafka.svg?style=plastic)](https://hub.docker.com/r/phenompeople/kafka/)
[![Docker Pulls](https://img.shields.io/docker/pulls/phenompeople/kafka.svg?style=plastic)](https://hub.docker.com/r/phenompeople/kafka/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Kafka 

Apache Kafka is a distributed streaming platform used for building real-time data pipelines and streaming apps. It is horizontally scalable, fault-tolerant, wicked fast, and runs in production in thousands of companies. Kafka requires a connection to a Zookeeper service.

### Supported tags and respective Dockerfile links

#### phenompeople/kafka

* **`latest`				([2.11/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/kafka/src/master/2.11/1.0.0/Dockerfile))**
* **`1.0.0`				([2.11/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/kafka/src/master/2.11/1.0,0/Dockerfile))**
* **`0.11.0.1`			([2.11/0.11.0.1/Dockerfile](https://bitbucket.org/phenompeople/kafka/src/master/2.11/0.11.0.1/Dockerfile))**
* **`0.10.0.0`			([2.11/0.10.0.0/Dockerfile](https://bitbucket.org/phenompeople/kafka/src/master/2.11/0.10.0.0/Dockerfile))**

#### Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)

### How to use this image 

1.  This image can be used by simply running 

```$ docker run --name=kafka -p 9092:9092 -td phenompeople/kafka```

Above command runs kafka container with port 9092 mapped to host and connecting to local zookeeper based on default server_config.properties. 

1. To make image run even after reboot use extra option --restart=always

```$ docker run --restart=always --name=kafka -p 9092:9092 -td phenompeople/kafka```

**Note:** If you remove the container all your data and configurations will be lost, and the next time you run the image the database will be reinitialized.

To avoid this loss of data, you should mount a volume that will persist even after the container is removed. If you are using default configuration mount the volume to /tmp/kafka-logs

1. To make image run even after reboot along with storage persistance use extra option --restart=always

```$ docker run --restart=always --name=kafka -p 9092:9092 -v /data:/tmp/kafka-logs -td phenompeople/kibana```

## Maintainers

* Rajesh Jonnalagadda (<rajesh.jonnalagadda@phenompeople.com>)

## License and Authors

**License:**	Apache License

**Author :** Phenompeople Pvt Ltd (<admin.squad@phenompeople.com>)