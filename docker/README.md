for port in {85..99}
do
   docker run -idt -p $port:80 nginx
   echo "nginx on port $port"
done

docker run -idt -p 27017:27017 mongo:2.6.7
docker exec -it c1620c902ba6 /bin/bash


docker pull dordoka/play-framework
sudo docker run --rm -it -v "/home/dordoka/Code:/home/play/Code" -p 9000:9000 -p 9999:9999 -p 8888:8888 dordoka/play-framework

sudo docker run --rm -it -p 9000:9000 -p 9999:9999 -p 8888:8888 dordoka/play-framework
docker exec -it c1620c902ba6 /bin/bash

docker run -idt -p 9000:9000 -p 9999:9999 -p 8888:8888 dordoka/play-framework

https://hub.docker.com/r/dordoka/play-framework/

docker pull rabbitmq
docker run -d --hostname my-rabbit --name some-rabbit rabbitmq:3
docker rm /rabbit-server
docker stop $(docker ps -q)
docker rm $(docker ps -aq)
cd /var/lib/docker/volumes
du -hs * | sort -h

docker volume ls -qf dangling=true

-----------DockerFile---------------
docker build -t="test" .

docker build -t docker-test --file ./Dockerfile .
docker run -t -i docker-test /bin/bash
docker commit -a "Sharad Vishe" -m "update file.txt" e5733af3d2ac docker-test-snap2
docker rmi -f e5733af3d2ac

sudo nano /etc/default/ufw
sudo ufw reload

--------------

sharing data volume between containers
------------------------------------------
docker create -v /data/docker/ubuntu --name datacontainer ubuntu:14.04
docker run -t -i ubuntu:14.04 /bin/bash

docker run -t -i --volumes-from datacontainer ubuntu /bin/bash
echo "this is 1st">file.txt
docker run -t -i --volumes-from datacontainer ubuntu:14.04 /bin/bash

echo "`date` This is from 1st container">>file.txt
echo "`date` This is from 2nd container">>file.txt


https://www.digitalocean.com/community/tutorials/how-to-work-with-docker-data-volumes-on-ubuntu-14-04


--------Sharing data volume between host and container-------------------
docker run -d -v /data/docker/ubuntu/nginxlogs:/var/log/nginx -p 5000:80 -i nginx

docker build -t gate-developer-8.1 --file ./Dockerfile .
docker run -it gate-developer-8.1-latest /bin/bash
