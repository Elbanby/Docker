# Docker Cheat Sheet

This is a simple Repo that I am going to keep updating, every time I learn something new in Docker.

It is my personal cheat sheet.

```
  This is a summary of the docker commands that I frequently use.

  I will try to keep this updated every time I enhance my skills in Docker.

  Keep in mind that this is just a quick reference and under no circumstances this sheet will scratch the surface of what Docker has to offer.
```


### How to get an image?

That is a very simple task, Use:

  ```
      Docker image <image_name>
  ```
  Example for running ubuntu:

    ```
        Docker pull ubuntu
        docker pull kalilinux/kali-linux-docker
    ```

### How to check for all available images

    ```
        docker images
    ```

### How to remove an image

      
       //Remove image if not in use
       Docker rmi <cha>    
       //Stop containers and force remove the image
       Docker rmi -f <cha>


    >Please note that images takes lots of space
    so constantly make sure you are erasing unused images
    and containers.

## How to create a container?

### Create a container:

    ```
        Docker run <container>
    ```

  Example Running a nginx container:

    ```
        Docker run --name nginx_server -d -p 80:80 <nginx>
    ```

  Example Running a mysql container:

  ```
        Docker run --name mysqlDB -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=True <mysql>
  ```

#### So lets explain...
      //This is the basic way to run a container
      Docker run <container>  
      //Specifies a port example 80:80
      -p
      //For detach. It means run in the back ground
      -d
      //For export, same as linux
      -e
      //To name your container. Very helpful
      --name
      //terminal
      -t
      //interactive
      -i

N.B:
>"To create a container with terminal use -it <kernel for example (bash)>"

N.B:
>"Always check the tons of documentation available online for how to run any
      container you needed."


### How to check which containers are running?

  ```
      Old way: Docker ps  (I personally like it)
      new way: Docker container ls
  ```

### How to see all containers created?

  ```
      Old way: Docker ps -a
      new way: Docker container ls -a
  ```

### How to remove a container?

  ```
      1- Docker stop <container_name OR cha>
      2- Docker rm <container_name OR cha>
  ```

### How to show the logs of a detached container?

  ```
      Docker container logs <container_name>
  ```

### How to see how a container was configured (in a JSON format)?

  ```
      Docker container inspect <container_name>
  ```

### How to monitor all running processes live?

  ```
      Docker container stats
  ```

### How to view processes running inside a container?

  ```
      Docker container top
  ```

### How to access a container that didn't have an -it option when configured?

  ```
      Docker container exec -it <kernal> <container_name>
  ```

### How to access a container that already has an -it tag on it?

  ```
      Docker container start -ai <container_name>
  ```
