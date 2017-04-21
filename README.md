# docker apache2 php 7.0 node.js npm

## Overview

This is a Dockerfile/image to build a container ubuntu:16.04 for apache2 and php, with php modules.

| Docker Tag 	| GitHub Release 	| Apache2 Version 	| PHP Version 	|
|------------	|----------------	|---------------	|-------------	|
| latest     	| Master Branch  	| 2.4.18        	| 7.0.15      	|


List PHP modules:
```
[PHP Modules]
amqp bcmath calendar Core ctype curl date  dom exif fileinfo filter ftp gd gettext gmp hash
iconv intl json ldap libxml mbstring mcrypt mongodb mysqli mysqlnd openssl pcntl pcre PDO
pdo_mysql Phar posix readline Reflection session shmop SimpleXML soap sockets SPL standard 
sysvmsg sysvsem sysvshm tokenizer wddx xml xmlreader xmlrpc xmlwriter xsl Zend OPcache zip zlib
[Zend Modules]
Zend OPcache
```
Addition:

`mc postfix`

## Links 
[Docker hub](https://hub.docker.com/r/lobsterk/docker-apache2-php7.0/)

## Quick Start

To pull from docker hub:

`docker pull lobsterk/docker-apache2-php7.0`

### Running
##### Simple run project 
```     
docker run -d -p 8080:80 \
      --rm \
      -v $(pwd)/www/:/var/www/html/ \
      --name test-docker \
      lobsterk/docker-apache2-php7.0
```

##### Run project with apache2 and php configs
```     
docker run -d -p 8080:80 \
      --rm \
      -v $(pwd)/www/:/var/www/html/ \
      -v $(pwd)/php/php.ini:/etc/php/7.0/apache2/php.ini \
      -v $(pwd)/apache2/apache2.conf:/etc/apache2/apache2.conf/ \
      -v $(pwd)/apache2/000-default.conf:/etc/apache2/sites-available/000-default.conf \
      --name test-docker \
      lobsterk/docker-apache2-php7.0
```

##### Enter container bash

`docker exec -it test-docker /bin/bash`