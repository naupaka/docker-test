Commands to build and run Dockerfile to make a Docker image with both ssh server and RStudio server

Based on images from the [rocker project](https://hub.docker.com/r/rocker/rstudio/).

Meant for local use and testing.    
Naupaka Zimmerman naupaka (at) gmail.com   
April 14, 2017   

see the [Docker docs](https://docs.docker.com/engine/examples/running_ssh_service/) and
[Stack Overflow](https://serverfault.com/questions/685697/multiple-commands-in-docker-cmd-directive)

*FIXME: root login not working, have to use user rstudio*

```sh
# build image from Dockerfile
# docker build -t rstudio-ssh .

# start container from image
docker run -P --name rstudio-ssh naupaka/rstudio-ssh

# find port on localhost linked to exposed ports on container (in second terminal) and connect
docker container ls --all
ssh -p theport rstudio@localhost
```

In a browser, go to localhost:theport and login with username:password
rstudio:rstudio
