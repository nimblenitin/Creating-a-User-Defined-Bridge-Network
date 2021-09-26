# Creating-a-user-defined-Bridge-Network

Steps to create a user defined bridge network and attach a container to the same-

```

1. Create a user-defined bridge network
$ sudo docker network create my-net1

2. Connect an nginx container to the my-net network. Also, publish port 80 in the container to port 8080 on the Docker host
$ sudo docker create --name my-nginx \
> --network my-net \
> --publish 8080:80 \
>  nginx:latest

3. Connect a running my-nginx container to an existing my-net network
$ sudo docker network connect my-net my-nginx

4. Inspect the my-nginx container and check the Networks
$ sudo docker container inspect my-nginx 

5. Disconnect the my-nginx container from the my-net network
$ sudo docker network disconnect my-net my-nginx

6. Inspect the my-nginx container and check the Networks
$ sudo docker container inspect my-nginx

```
