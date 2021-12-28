# keycloak-ansible-hello-world


Sample playbook using the ansible [keycloak module](https://galaxy.ansible.com/cesarvr/keycloak) which is able to publish/unpublish resource to a Keycloak and Red Hat Single Sign-On. 

### Usage 

First make sure you have Python3 and the [Keycloak Python API](https://pypi.org/project/kcapi/) which is used to communicate with the Keycloak endpoints and then install the [Ansible module](https://galaxy.ansible.com/cesarvr/keycloak).  
Once you got those just run: 

```sh
ansible-playbook create.yml 
```

And it will run this sample which contain: 
- A realm called heroes. 
- A set of users that belongs to the DC/Marvel. 
- A set of clients. 
- A the groups Marvel/DC. 
