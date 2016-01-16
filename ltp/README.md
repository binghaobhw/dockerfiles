# LTP Dockerfile

Dockerfile of [LTP (Language Technology Platform)](https://github.com/HIT-SCIR/ltp) for [Docker](https://www.docker.com/).

## Base Docker Image

[ubuntu:14.04](https://hub.docker.com/_/ubuntu/)

## LTP Version

[3.3.0](https://github.com/HIT-SCIR/ltp/releases/tag/v3.3.0)

## Model Data

Since the model data are very big, this image doesn't include them. You can download them from [Baidu Cloud](http://pan.baidu.com/share/link?shareid=1988562907&uk=2738088569#path=%252Fltp-models%252F3.3.0).

When start a container, you need to mount the model data directory on the host to `/ltp_data` on the container.

## Usage

Suppose the model data directory is `/ltp_data` on your Docker host.

```console
$ ls /ltp_data
changelog  cws.model  md5.txt  ner.model  parser.model  pos.model  srl  version
```

To start a ltp server container publishing the container port to the host:

```console
docker run -p 12345:12345 -v /ltp_data:/ltp_data -t scorpio147wbh/ltp:3.3.0
```
