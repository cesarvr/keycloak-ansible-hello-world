# keycloak-ansible-hello-world


Sample playbook using the ansible [keycloak module](https://galaxy.ansible.com/cesarvr/keycloak) which is able to publish/unpublish resource to a Keycloak and Red Hat Single Sign-On (RHSSO). 

### Usage 

First make sure you have:
- [Python3](https://docs.fedoraproject.org/en-US/fedora/f33/release-notes/developers/Development_Python/). 
- [Keycloak Python API](https://pypi.org/project/kcapi/) which is used to communicate with the Keycloak endpoints. 
- Then install the [Keycloak Ansible module](https://galaxy.ansible.com/cesarvr/keycloak).  


Once you got those you can run this sample playbook: 

```sh
ansible-playbook create.yml 
```

And it will run this sample which contain: 
- A realm called heroes. 
- A set of users that belongs to the DC/Marvel. 
- A set of clients. 
- A the groups Marvel/DC. 


> This will run against an ephemeral 90 days RHSSO instance running in Openshift.IO so is not sure that this will always work. You are invited to deploy your own instance and running this playbook against it. 
