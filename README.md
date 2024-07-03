# Docker Container Deployment using Ansible

To deploy docker-compose application using Ansible.

## Build

The container image is build using GitHub Actions and pushed to DockerHub.

Make sure you updated the secrets before running the pipeline. Follow the below steps:
- Go to Settings
- Secrets and Variables
- Actions
- Under repository Secrets to add the DockerHub credentials as secrets. 
Add DOCKER_USERNAME and DOCKER_PASSWORD. 

## Deploy

Use the below command to deploy the Ansible playbook.

```sh
ansible-playbook --inventory inventory deployer.yml 
```

Add ```sh -vv ``` flag to the above command to get more detailed log.
