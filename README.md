This repo demonstrates a simple site visit counter in a PHP docker.

# How to build
```
docker build -t zenlab/visit-counter .
```

# How to run with docker image built from Dockerfile
```
docker run --rm \
  -p 80:80 \
  --name visit-counter \
  zenlab/visit-counter
```
or, run with official php docker image
```
docker run --rm \
  -p 80:80 \
  --name php \
  -v "$PWD/scripts":/var/www/html \
  php:7.0-apache
```

# How to overwrite the web root with a volume at runtime
```
docker run --rm \
  -p 80:80 \
  --name visit-counter \
  -v "$PWD/scripts":/var/www/html \
  zenlab/visit-counter
```

# How to access
```
http://localhost/visit.counter
```
or
```
http://localhost/php.info
```

# Acknowledgments

Code adapted from http://justintadlock.com/web-design/counter

Docker image extended from https://hub.docker.com/_/php/
