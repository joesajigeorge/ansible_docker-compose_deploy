# Docker Container Deployment using Ansible

To deploy docker-compose application using Ansible.

## Build

The container image is build using GitHub Actions and pushed to DockerHub.

Make sure you updated the secrets before running the pipeline. Follow the below steps:
- Go to Settings
- then Secrets and Variables
- Select Actions
- Under repository Secrets, add the DockerHub credentials as secrets (DOCKER_USERNAME and DOCKER_PASSWORD). 

## Deploy

Before deployment update the inventory file. In my example I am deploying to the same server.

Use the below command to deploy the Ansible playbook.

```sh
ansible-playbook --inventory inventory deployer.yml 
```

![image](https://github.com/joesajigeorge/docker_deploy/assets/32813415/53778a7e-cd36-478c-8360-a2caecaa5d48)

Add ```sh -vv ``` flag to the above command to get more detailed log.

Once deployment has been completed, ssh to the remote system and check the container status.

```sh
docker ps
```
![image](https://github.com/joesajigeorge/docker_deploy/assets/32813415/de0736bb-0200-4416-9a43-319c9bf143bb)


