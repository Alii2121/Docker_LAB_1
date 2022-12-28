### LAB1

1- RUN Hello-World

```bash 
docker run hello-world 
```

2- Check status 

```bash 
docker container ps -a 
```

3- start stopped container

```bash 
# 8ab16d9 stand for ID
docker start 8ab16d9 
```
4- Remove container 

```bash 
docker container rm 8b9581a6
```
5- Remove Image
```bash
docker image rm 1e415454686a
```

6- Run CentOs in interactive mode
```bash 
docker run -it centos
```

7- Run a command inside the container
```bash
echo "docker"
```

8- Touch a file
```bash
touch hello-docker.txt
```

9- Stop the container and remove it, then a comment about the file I created
```bash
docker stop <ID>
docker container rm <id>
# The file created inside is deleted because there's no volume attached to it and containers lose it's inside data if deleted
```

10- Remove stopped containers
```bash
docker container prune
```
11- Run httpd with name apache and attach volume
```bash
docker volume create volume1 
sudo docker run -d -v volume1:/usr/local/apache2/htdocs --name apache httpd


```
12-remove container
```bash
docker container rm apache
```
13-run new container and attach same volume

```bash
sudo docker run -d -v volume1:/usr/local/apache2/htdocs -p 9898:80  --name apache httpd
```

14-run container with no volume and then access it and create static html file
```bash
 sudo docker run -it  -p 9898:80  --name apache5 httpd /bin/bash
cd /usr/local/apache2/htdocs/ 
touch index.html
```

15- Commit an image 
```bash
docker commit <id>
```

16- Dockerfile
```bash
FROM nginx
RUN rm /etc/nginx/nginx.conf /etc/nginx/conf.d/default.conf
COPY content /usr/share/nginx/html
COPY conf /etc/nginx
VOLUME /usr/share/nginx/html
VOLUME /etc/nginx
```
17- 
```bash
docker run -d -p 8099:8080 -e  MYSQL_ROOT_PASSWORD='P4sSw0rd0!.Mount'  -v my_sqldata:/var/lib/mysql --name app-database mysql
```

 
