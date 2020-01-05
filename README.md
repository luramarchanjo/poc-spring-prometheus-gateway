# Overview

The Prometheus Pushgateway exists to allow ephemeral and batch jobs to expose their metrics to Prometheus. Since these kinds of jobs may not exist long enough to be scraped, they can instead push their metrics to a Pushgateway. The Pushgateway then exposes these metrics to Prometheus.

# Setup

## Prometheus Push Gateway

First, run the command bellow:

~~~
docker run -d --net=host --name=prometheus-pushgateway prom/pushgateway:latest
~~~

Second, open the browser and access the address `http://localhost:9091`

## Application

Start the application

~~~
mvn spring-boot:run
~~~

# Testing

Call the endpoint `http:\\localhost:8080\hello`

## Curl

~~~
curl -i http://localhost:8080/hello
~~~