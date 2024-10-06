
# `` Docker `` 

## `` What is Docker? ``

- Virtualization software 
- Makes developing and deploying Applications easier
- Packages application with all the necessary dependencies, configuration, system tools and runtime

### `` Before Containers ``

- Each developer needs to install and configure all services directly to their OS on their local machine
- Installation process is different for each OS environment
- Many steps, where something can go wrong

### `` How containers work(top level overview) ``

- With docker, the service you need is packaged in one single environment 
- Postgres packaged with all dependencies and configs 
- Now you don't have to go and install and run all the commands but 
- just run one docker command and get all the setup ready...
* Commands are same for all OS
* Command same for all services
* Easy to run different versions of the same app without any conflicts
  
## `` Deployment process before container ``

~ Development team setups up and Artifact(instruction on how to install and configure app on the server)
~ For this scenario - installation and configuration's done directly on the server's OS
* Dependency version conflicts... etc...
  
