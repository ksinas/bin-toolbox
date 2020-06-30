# Toolbox scripts

## json-prettify

Will output compressed json to multiline readable format.

Usage
```
cat test.json | json-prettify > pretty-file.json
```

## open

Will open a folder on ubuntu

Usage
```
open .
```

## sshdevice

Will ssh to device without checking a fingerprint. Useful when dev devices get flashed. 

You need to set ENV $PI_PASSWORD

Usage
```
sshdevice 192.168.1.20
```

## tailgrep

Allows to tail the file and filter with grep

Usage
```
tailgrep some.log error
```

## test-container

This can be handy to test a docker container. You need to edit the file to set a correct path to your
docker-compose.yml file which should look something like this:
```yaml
version: '3'
services:
  myservice:
    network_mode: "host"
    image: ${DOCKER_IMAGE}
    restart: always
    hostname: myservice
    environment:
      - MONGO_URL=mongodb://127.0.0.1:27017/myservice
      - ROOT_URL=https://my.cloud.dev/
      - PORT=3000
```

Usage
```
test-container namespace/container
```
