# Docker Installation Guide for Linux

This guide will walk you through the steps to install Docker on both Ubuntu and CentOS.

## Table of Contents

- [Docker Installation on Ubuntu](#docker-installation-on-ubuntu)
- [Docker Installation on CentOS](#docker-installation-on-centos)
- [Post-Installation Steps](#post-installation-steps)

## Docker Installation on Ubuntu

1. **Update your system:**
    ```bash
    sudo apt-get update
    sudo apt-get upgrade
    ```

2. **Install required packages:**
    ```bash
    sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
    ```

3. **Add Docker’s official GPG key:**
    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    ```

4. **Set up the stable repository:**
    ```bash
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    ```

5. **Update the package database with Docker packages from the newly added repo:**
    ```bash
    sudo apt-get update
    ```

6. **Install Docker CE:**
    ```bash
    sudo apt-get install docker-ce
    ```

7. **Verify Docker installation:**
    ```bash
    sudo systemctl status docker
    ```

## Docker Installation on CentOS

1. **Update your system:**
    ```bash
    sudo yum update -y
    ```

2. **Add the Docker repository:**
    ```bash
    sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    ```

3. **Install Docker CE:**
    ```bash
    sudo yum install docker-ce -y
    ```

4. **Start and enable Docker:**
    ```bash
    sudo systemctl start docker
    sudo systemctl enable docker
    ```

5. **Verify Docker installation:**
    ```bash
    sudo systemctl status docker
    ```

## Post-Installation Steps

1. **Run Docker commands without `sudo`:**

    ```bash
    sudo usermod -aG docker $USER
    ```

    Log out and log back in so that your group membership is re-evaluated.

2. **Test Docker installation:**

    ```bash
    docker run hello-world
    ```

This should download and run the `hello-world` image, confirming that Docker is installed correctly.

---

Feel free to modify this README.md file to better suit your needs!
