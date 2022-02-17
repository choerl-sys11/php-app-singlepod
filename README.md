# NGINX PHP-FPM in one Pod

## Purpose

This is a demo PHP application to print out PHP-info.
The application is served by a php-fpm container behind nginx.

## Scenario

- php-fpm and nginx run in the same Pod

- in this minimalistic example not even a service is used to expose php-fpm on port 9000 because
both containers are in the same Pod and so nginx can reach phpfpm by the name of "localhost:9000".

## How to use

### Deploy

`kubectl apply -f .`

Create a port-forward:

`kubectl -n demo port-forward phpfpm-nginx-example 8080:80`

### Access application

Browse: http://localhost:8080

### Uninstall

`kubectl delete -f .`

## Reference
https://gist.github.com/petitviolet/d36f33d145d0bbf4b54eb187b79d0244

https://mailman.nginx.org/pipermail/nginx/2008-November/008311.html

## Info

Author: c.hoerl@syseleven.de