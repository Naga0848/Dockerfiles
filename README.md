#### Dockerfiles

#### In this Repo, we are just understanding the different instructions which we use in our Dockerfile and that is the reaon we mention CMD and give a sleep command to run the container.


#### Commands to install Docker on an EC2

    sudo dnf -y install dnf-plugins-core

    sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo

    sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

    sudo systemctl restart docker

    sudo systemctl enable --now docker

    sudo usermod -aG docker ec2-user


#### add your normal user to docker group  -- because we cannot run the docker commands as a normal ec2-user


    exit, after adding normal user and re-login and start using the docker commands without giving sudo

    Again after logging in, we have to start and enable the docker

    sudo systemctl start docker
    sudo systemctl enable docker



 # My Docker Credentials
    username - nagashankar1992332


 #### Docker Basic Commands

        docker images 

        docker pull <image-name>:<tag/version> --> get the image

        docker create nginx

        docker ps -a --> all containers including all status

        docker start <container-ID>

        docker rm <container-ID>

        docker run <image>:<tag> -> pull image + create container + start container

        docker run -d nginx --> detach the screen

        docker ps a -q ====> to display all the containers

        docker rm -f 'docker ps a -q'  ====> to delete all the containers at a time

        0-65,535   === total no of ports for a container or a server

        docker run -d -p 80:80 nginx

        docker exec -it nginx bash   ===> to login to a container

        docker inspect container-name/container-ID


#### General Notes

    How can you create custom images to your applications?

    Dockerfile --> a set of instructions to create customised images

    FROM
    =========
    FROM almalinux:9

    docker build -t from:v1 . --> current directory has Dockerfile

    RUN
    =========
    RUN commands

    RUN instructions configure the image like installing packages, doing some configurations, etc..
    RUN executes at the time of image creation

    systemctl start nginx --> etc/systemd/system/nginx.service

    docker pull nginx -> first it checks locally, if it does not exist it checks in hub

    CMD
    =========
    CMD executes at the time of container creation i.e at the time of docker run. there should be only one CMD instruction inside Dockerfile

    COPY
    =========
    copies the code from local to container

    ADD
    =========
    COPY and ADD both copies the code from local to container. but it has two more advantages

    1. it can directly fetch the file from internet
    2. it can directly untar the file into container


#### Understanding the Docker Instructions One-By-One

    FROM
  ![App Screenshot](images/from.png)      

            docker build -t from:v1   >>> command to build an image
            
            docker images >>> to view the images
            
            docker run -d --name from from.v1:latest  >>> indicates that we are running a container whose name is from and it is created from an image named from.v1:latest
        