# Minikube Installation Guide for Ubuntu

# Launch the tito medium instance this is necessary

# Step 1: Update System Packages
      sudo apt update  

# Step 2: Install Required Packages
      sudo apt install -y curl wget apt-transport-https

# Step 3: Install Docker
      sudo apt install -y docker.io

# Start and enable Docker.
      sudo systemctl enable --now docker

# Add current user to docker group (To use docker without root)
      sudo usermod -aG docker $USER && newgrp docker

# Step 4: Install Minikube
      curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

# give the exicutive permission
      chmod +x minikube

# move it into your path
      sudo mv minikube /usr/local/bin/

# Step 5: Install kubectl
# Download kubectl, which is a Kubernetes command-line tool
      curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

#  Make it executable
      chmod +x kubectl

# move it into your path:
      sudo mv kubectl /usr/local/bin/

# Step 6: Start Minikube
      minikube start --driver=docker --vm=true 
