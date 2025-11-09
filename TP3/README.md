# 3-1 Document your inventory and base commands

The inventory is used to connect to the remote server by presising our role, ssh key and host url. 

To connect we use this command as a base:
```ansible all -i inventories/setup.yml```
We can use command by adding shell after this base for exemple :
```ansible all -i inventories/setup.yml -m apt --version```

# 3-2 Document your playbook

The playbook file specifies all the roles and the task they execute. Dividing our setup like this allows our code to be clearer and easier to modify.
```
roles:
    - docker
    - network
    - db
    - app
    - proxy
```
This means we have these 5 roles that will execute their task/main.yml on our server.
Docker installs all prerequisites such as docker on our debian server, network creates the dockers networks needed for our applications.
db, proxy and app start by pulling the last version of our docker images and launches them with the configuration needed.
