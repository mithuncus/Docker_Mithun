Docker command s





**72.3.2.** aws data cent lo , provided by aws network  through ethernet

eth0: flags=463<UP,BROADCAST,RUNNING,MULTICAST>  mtu 900
        inet **72.3.2.**  netmask 5.5.0.0  broadcast 72.3.5.5
        inet6 fe80::77:9aff:fe:9a85  prefixlen 64  scopeid 0x<link>
        ether 02:77:9a::9a:85  txqueuelen 000  (Ethernet)
        RX packets 69  bytes 89872 (857.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 60532  bytes 69543 (6.6 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


Docker n/w 

docker0: flags=463<UP,BROADCAST,RUNNING,MULTICAST>  mtu 500
        inet 72.7.0.  netmask 5.5.0.0  broadcast 72.7.5.5
        inet6 fe80:::3fff:fe43:8a47  prefixlen 64  scopeid 0x<link>
        ether 02::3f:43:8a:47  txqueuelen 0  (Ethernet)
        RX packets 5590  bytes 5865 (572.4 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 5458  bytes 6877 (.4 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

docker inspect container id

docker ps
docker inspect a52
container can not communicate with each other through if they use docker default n/w
host and bridge

by default docker create bridge n/w

roboshop project can create its own network, we need to create 
docker network 
docker network
docker network create roboshop
docker network ls
for removing all the images --> docker  rm -f 'docker ps -a -q'     

 0:57 docker build -t web: .
   docker run -d -p 80:80 --name web --network=roboshop web:
   docker ps
  79  : docker ps -a
  git pull
     2: ls -l
  2   2:35 docker images
  3   2:52 docker rm -f 7f2a0de3fc
  4   4:05 ls
  5   4:0 docker ps
  6   4:5 docker images
  7   4:35 docker rm -f 7f2a0de3fc
  8   4: docker rm -f web
  9   4:47 docker images
  0   5:3 docker logs web
     5:22 docker logs 7
  2   5: pwd
  3   3: cd Docker_Mithun/Roboshop_Docker/web
  4   3: docker ps -a
  5   3:43 docker image ls
  6   32:09 docker exec -d --name=web web:
  7   32: docker run -d --name=web web:
  8   32: docker ps
  9   32: docker ps -a
  0   :0 docker logs web
     : ls -la
  2   : less roboshop.con
  3   : less roboshop.conf
  4   :7 clear
  5   :32 docker run -it --name=nginx nginx
  6   :38 docker run -it -d --name=nginx nginx
  7   :43 docker ps
  8   :5 docker rm -f nginx
  9   :53 docker run -it -d --name=nginx nginx
  0   :57 docker ps
     35:6 docker exec -it nginx bash
  2   39:39 docker rm -f nginx
  3   39:44 docker rm -f web
  4   39:46 ls -la
  5   39:54 vim roboshop.conf
  6   40: vim Dockerfile
  7   40:37 clear
  2   40:44 docker build -t web: .
  2   40:58 docker run -it -d --name=web web:
  2   4: docker rm -f b
  2   4:3 clear
 2   4: docker run -it -d --name=web --network=roboshop web:
 3   4: docker network ls
 4   4:43 docker network inspect roboshop
 5   4:53 clear
 6   4:55 docker ps
 7   :05 docker rm web
 8   :08 docker rm -f web
 9   : docker run -it -d -p 80:80 --name=web --network=roboshop web:
  0   : curl localhost
     :39 clear
  2   :47 curl localhost/api/catalogue/health
  3   :57 curl localhost/api/catalogue/categories
  4   44:07 docker exec -it web bash
  5   47:06 curl localhost/api/catalogue/products/Robot
  6   55:08 sudo -i
  7   56: clear
  8   3: cd Docker_Mithun/Roboshop_Docker/web
  9   3: docker ps -a
  0   3:43 docker image ls
     32:09 docker exec -d --name=web web:
  2   32: docker run -d --name=web web:
  3   32: docker ps
  4   32: docker ps -a
  5   :0 docker logs web
  6   : ls -la
  7   : less roboshop.con
  8   : less roboshop.conf
  9   :7 clear
  0   :32 docker run -it --name=nginx nginx
     :38 docker run -it -d --name=nginx nginx
  2   :43 docker ps
  3   :5 docker rm -f nginx
  4   :53 docker run -it -d --name=nginx nginx
  5   :57 docker ps
  6   35:6 docker exec -it nginx bash
  7   39:39 docker rm -f nginx
  8   39:44 docker rm -f web
  9   39:46 ls -la
  0   39:54 vim roboshop.conf
     40: vim Dockerfile
  2   40:37 clear
  3   40:44 docker build -t web: .
  4   40:58 docker run -it -d --name=web web:
  5   4: docker rm -f b
  6   4:3 clear
  7   4: docker run -it -d --name=web --network=roboshop web:
  8   4: docker network ls
  9   4:43 docker network inspect roboshop
  0   4:53 clear
     4:55 docker ps
  2   :05 docker rm web
  3   :08 docker rm -f web
  4   : docker run -it -d -p 80:80 --name=web --network=roboshop web:
  5   : curl localhost
  6   :39 clear
  7   :47 curl localhost/api/catalogue/health
  8   :57 curl localhost/api/catalogue/categories
  9   44:07 docker exec -it web bash
  0   47:06 curl localhost/api/catalogue/products/Robot
     55:08 sudo -i
  2   56: clear
  3  :04:55 pwd
  4  :04:56 ll
  5  :05:0 cd roboshop-docker/
  6  :05:0 ll
  7  :05:08 cd ../
  8  :05:09 ll
  9  :05:2 cd Docker_Mithun/
  0  :05:3 ll
    :05: cd Roboshop_Docker/
  2  :05: ll
  3  :05: cd web/
  4  :05: ll
  5  :05:32 cat Dockerfile 
  6  :05:39 cd roboshop.conf
  7  :05:44 cat roboshop.conf
  8  :06: ww
  9  :06:5 w
  0  :06:50 history
    :09:36 docker ps
  2  :5:06 pwd
  3  :5:07 ll
  4  :5:4 cat roboshop.conf
  5  :5:48 pwd
  6  :5:50 ll
  7  :6:0 cp roboshop.conf roboshop.conf_working one
  8  :6:08 sudo cp roboshop.conf roboshop.conf_working one
  9  :6: sudo cp roboshop.conf roboshop.conf_working
    :6: ls
  3  :6: git pull
  32  :6: ll
     cat roboshop.conf
    docker ps
  35  :6:46 history
  36  :6:55 docker ps
  37  :7:05 docker  rm -f web
  3  :7:09 docker ps
  3  ::3 docker images
  3  ::47 curl localhost/api/catalogue/health
  3  :4 docker build -t web: .
  322  : docker images
  3  :44 docker exec -it nginx
  3  :48 docker exec -it nginx bash
  3  :22:57 docker ps
  3  ::22 docker run -it -d --name=nginx nginx
  3  :: docker ps
  3  ::32 docker exec -it nginx bash
  3  :39: pwd
  0  :40: ll
    :4: docker ps
  2  :4:54 docker images
  3  :4:58 docker ps
  4  :: docker run -it -d -p 80:80 --name=web --network=roboshop web:
  5  ::37 docker ps
  6  :54:7 docker logs catalogue
  7  :55: pwd
  8  :55: ls -lhrt
  9  :55:39 cat docker-compose.yaml 
  0  :56:04 cat Dockerfile 
for building an image :
docker build -t web: .

for running an image as a container 

docker run -it -d -p 80:80 --name=web --network=roboshop web:

For removing the conatainer command 
docker rm -f web
docker rm -f catalogue
docker rm -f mongodb

docker exec -it cointainerID bash  --> for login to the container inside
docker logs containerid 
docker logs web
docker logs catalogue


