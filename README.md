# Dockerfiles

# Commands to execute the docker on an EC2

sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo systemctl restart docker

sudo systemctl enable --now docker


# add your normal user to docker group  -- because we cannot run the docker commands as a normal ec2-user

sudo usermod -aG docker ec2-user

exit, after adding normal user and re-login and start using the docker commands without giving sudo

Again after logging in

sudo systemctl start docker

sudo systemctl enable docker

# In this Repo, we are just understanding the different instructions which we use in our Dockerfile and that is the reaon we mention CMD and give a sleep command to run the container.


 # My Docker Credentials
 username - nagashankar1992332


 # Basic Commands

docker images 
docker pull <image-name>:<tag/version> --> get the image

docker create nginx
docker ps -a --> all containers including all status
docker start <container-ID>



docker rm <container-ID>
docker run <image>:<tag> -> pull image + create container + start container
docker run -d nginx --> detach the screen