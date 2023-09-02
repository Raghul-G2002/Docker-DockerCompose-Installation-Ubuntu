# Docker and Docker Compose Installation of Ubuntu 20.04 Machine
Installation guide for Docker and Docker Compose on Ubuntu 20.04 Machine. 

# Install Docker and Docker Compose in Ubuntu 20.04

1. Uninstall the previous versions of the Docker present in the machine: <br/>
``` for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done ```

2. Update the apt package and install the all certificates to allow the repo to use over HTTPS: <br/>
```sudo apt-get update```
```sudo apt-get install ca-certificates curl gnupg```

3. Add Docker's official GPG Key:<br/>
```sudo install -m 0755 -d /etc/apt/keyrings```<br/>
```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg```<br/>
```sudo chmod a+r /etc/apt/keyrings/docker.gpg```

4. Use the following command to set up the repository: <br/>
```echo \ "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \ "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \ sudo tee /etc/apt/sources.list.d/docker.list > /dev/null```
  
5. Update the apt package index: <br/>
```sudo apt-get update```

6. Install the Docker Engine, containerd, and Docker Compose: <br/>
```sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin```

7. Check the version of the Docker and Docker Compose: <br/>
```docker --version```<br/>
```docker compose version```
