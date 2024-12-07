# Create your droplet configure your firewall rules, then update the server

## Install Docker on the droplet
-snap install docker(for latest version)

## Ensure data persists
you can always check for up to date informations how to configure volumes in the official documentation 
-checking the official nexus image:https://hub.docker.com/r/sonatype/nexus
-checking the docker volumes documentation: https://docs.docker.com/engine/storage/volumes/
-$ docker run -d --name nexus-data sonatype/nexus echo "data-only container for Nexus"
-$ docker run -d -p 8081:8081 --name nexus --volumes-from nexus-data sonatype/nexus

## Nexus user automatically created this way
see documentation: https://hub.docker.com/r/sonatype/nexus/tags