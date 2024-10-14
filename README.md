# Docker
## summary
```
docker pull    <image_name>     --> image pull from repo
docker images ---> show images
docker run          <image name >    <cmd>  ---> create or run container
       --name
  -d (for background)
       -it   (excute into container during start)
docker ps ---> to show running container
docker ps  -a ---> to show all container
docker start  <container name>  ---> to start stop container
docker stop   <conatiner_name>  ---> to stop a running container
docker rm   <container_name> ---> to remove stop container
docker rm -f  <container_name> ---> to remove running container also
docker cp  <container_name>:<PATH> ---> to copy file into container
docker rmi <container_name>  ---> remove  images
```
```
wget https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1983  ls
 1984  unzip carvilla.zip 
 1985  ls
 1986  cp -r carvilla-v1.0 apache/
 1987  ls
 1988  cd apache/
 1989  ls
 1990  curl -o https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1991  curl -O https://www.free-css.com/assets/files/free-css-templates/download/page296/carvilla.zip
 1992  ls
 1993  rm carvilla.zip 
 1994  ls
 1995  vim Dockerfile
 1996  cd docker/
 1997  cd apache/
 1998  ls
 1999  vim Dockerfile 
 2000  docker build -t myweb .
 2001  docker run -d -p 1122:80 myweb
 2002  docker ps
 2003  ifconfig 
 2004  ls
 2005  cat Dockerfile 
 2006  ls
 2007  wget https://www.free-css.com/assets/files/free-css-templates/download/page296/neogym.zip
 2008  ls
 2009  unzip neogym.zip 
 2010  ls
 2011  vim Dockerfile 
 2012  docker build -t web2 .
 2013  docker run -d -p 1133:80 web2
 2014  docker ps
 2015  ls
 2016  vim neogym-html/
 2017  vim neogym-html/index.html 
 2018  docker run -d -p 1133:80 web2
 2019  docker run -d -v /home/akash/docker/apache/neogym-html:/var/www/html -p 1144:80 web2 
 2020  docker ps
 2021  cd neogym-html/
 2022  ls
 2023  vim index.html 
 2024  ls
 2025  rm -r *
 2026  cd ..
 2027  ls
 2028  cp -r carvilla-v1.0/. neogym-html/.
 2029  cd neogym-html/
 2030  ls
 2031  rm -r *
 2032  ls
 2033  vim index.html
docker ps
 2038  docker inspect angry_tesla 
 2039  curl 172.17.0.4
 2040  ls
 2041  docker images
 2042  docker tag web2 aakashgaur57/web2
 2043  docker images
 2044  docker login 
 2045  docker push aakashgaur57/web2
 2046  history 



```

# 14OCT docker
```
akash@akash:~$ docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=q123 -e MYSQL_DATABASE=demo -e MYSQL_USER=akash -e MYSQL_PASSWORD=q123 -p 2233:3306 mysql
+ **akash@akash:~$** docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                                  NAMES
96bf3c44da9e   mysql     "docker-entrypoint.s…"   4 seconds ago    Up 3 seconds    33060/tcp, 0.0.0.0:2233->3306/tcp, :::2233->3306/tcp   mysql
+ **akash@akash:~$** mysql -h 127.0.0.1 -u akash -p -P 2233
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 9.0.1 MySQL Community Server - GPL

Copyright (c) 2000, 2024, Oracle and/o

```
