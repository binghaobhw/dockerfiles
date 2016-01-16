# Solr Dockerfile

Dockerfile of [Solr](http://lucene.apache.org/solr/) for [Docker](https://www.docker.com/).

## Base Docker Image

[scorpio147wbh/server-jre](https://hub.docker.com/r/scorpio147wbh/server-jre/)

## Solr Version

5.3.1

## Usage

Suppose the collection1 directory is `/collection1` on your Docker host.

```console
$ ls /collection1
conf  core.properties  data
```

To start a solr instance:

```console
$ docker run -d -p 8983:8983 -v /collection1:/opt/solr/server/solr/collection1 --name solr scorpio147wbh/solr:5.3.1
```
