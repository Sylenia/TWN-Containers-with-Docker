# configure Nexus 

## Create Docker Repository
configure and create Docker repository in Nexud: docker(hosted) - select name and store for the repo
use the repo's URL

## Role
create and configure a Nexus role that has access to docker repository - give docker hosted privilage

## Configure docker repository
set http port to a different endpoint that out app is using and save it
you can check if the config was successful in your droplet using netsat -lnpt command

## Firewall config on your droplet
Create a custom firewall rule that will allow access to it with the port number you defined in the docker repo

## Configure Nexus Realm
select docker bearer token realm and activate it (necessary for docker/config.json)

## Config insecure registry for docker in daemon.json
update the file using insecure registries, and add your domain
in docker desktop, configure this in docker engine!

## Login
now you can use the docker login command specifying your ip address and configured port number
also giving your nexus credentials

# Push images to Nexus
build your image -docker build -t my-app:1.0 .
tag your image -docker tag my-app:1.0 <IP:Port>/my-app:1.0
push your image -docker push <IP:Port>/<tag>