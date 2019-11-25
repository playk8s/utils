# utils [![Build Status](https://travis-ci.org/playk8s/utils.svg?branch=master)](https://travis-ci.org/playk8s/utils)

Docker image with tools like curl, wget, ping, netcat, nslookup,host, dig, psql, mysql, swaks etc.

## Use Case

When using containers you might want to test the connectivity between the containers. Your application containers won't be having tools like curl, ping, psql client etc. So you can start a one-off container using this image and test your application.

For example, to run a one-off container in Kubernetes:

```
kubectl run --rm utils -it --generator=run-pod/v1 --image amitamit281/utils bash

# You will be seeing a bash prompt
$ psql -h hostname -U test -d test
...
...
$ exit
```

**Note:** `--rm` option will delete the  `pod` after exiting from the container

## General Usage

```
$ docker pull amitamit281/utils
$ docker run --rm -it amitamit281/utils bash

# inside the container
$ ping google.com
$ ifconfig
...
$ exit
```

## Contributing

Build and run tests:

```
$ ./build
```
