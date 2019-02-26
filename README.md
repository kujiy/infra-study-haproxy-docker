
```
cd weba
docker-compose up -d

cd webb
docker-compose up -d

cd haproxy
docker-compose up -d

# access with browser

http://${IP}:8001/
http://${IP}:8002/
http://${IP}:9000/
http://${IP}/

##
docker inspect weba_apache_1 | grep IPAddress
docker inspect webb_apache_1 | grep IPAddress
docker inspect haproxy | grep IPAddress

docker network create my_network --subnet 172.27.27.0/24 --ip-range 172.27.27.0/24 --gateway 172.27.27.1

docker network ls

docker network inspect my_network

##
cd weba
docker-compose -f docker-compose-with-network.yml up -d --force-recreate

cd webb
docker-compose -f docker-compose-with-network.yml up -d --force-recreate

# access with browser

cd haproxy
docker-compose -f docker-compose-with-network.yml up -d --force-recreate

# access with browser
docker network connect my_network haproxy

```
