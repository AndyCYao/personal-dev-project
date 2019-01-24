## use this to create an amazon ec2 docker machine

    docker-machine create --driver amazonec2 \
                        --amazonec2-instance-type t2.medium \
                        --amazonec2-open-port 9092 \
                        --amazonec2-open-port 3888 \
                        --amazonec2-open-port 2181 \
                        --amazonec2-root-size 128 \
                        --amazonec2-region us-west-2 \
                        andy-dev
                        


## Notes:
Apache image works when i connect to 

    http://192.168.99.100:8080/main.html

where 192.168.99.100 is IP of my docker machine

When i run the same via

http://ec2-34-220-119-201.us-west-2.compute.amazonaws.com:8080/main.html

it also works, but I have to make sure I have opened port 8080 in aws' security
group