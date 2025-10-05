# Dockerfiles

# Commands to execute the docker on an EC2

sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo systemctl restart docker

sudo systemctl enable --now docker

# add your normal user to docker group

sudo usermod -aG docker ec2-user