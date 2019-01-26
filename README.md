## Intro
This is a personal project to run multiple websites on a docker compose 
apache / flask set up

### use this to create an amazon ec2 docker machine

    docker-machine create --driver amazonec2 \
                        --amazonec2-instance-type t2.micro \
                        --amazonec2-open-port 9092 \
                        --amazonec2-open-port 8080 \
                        --amazonec2-root-size 128 \
                        --amazonec2-region us-west-2 \
                        andy-dev-1
                        

### Notes:
- Instead of using the official docker apache2 image, I am using debian:jessie, and installing apache2 from there. this is because I am more familiar with the symbolic linking workflow.

(aside, you can use `docker build . -t debian-apache:v1` to build your own image, then `docker run debian-apache:v1` to run it)


- Apache image works when i connect to 

    http://192.168.99.100:8080/main.html

where 192.168.99.100 is IP of my docker machine

When i run the same via

http://ec2-34-220-119-201.us-west-2.compute.amazonaws.com:8080/main.html

it also works, but I have to make sure I have opened port 8080 in aws' security
group

- I registered two name

    testwebsite1.ml
    testwebsite3.ml

from frenom, they expire in 3 months

__TODO remove this when the project is over__
- I created an elastic IP 34.216.28.49 and associated it to the andy-dev-1 i created. 
- I created an Amazon Hosted Zone, created two A record that points to the elastic IP
- I go back to Frenom, and changed the Nameserver to point to the 4 name servers in the Hosted Zone



