# Commands to build and run Dockerfile to make a Docker image of with both ssh server and RStudio server listening
# Meant for local use
# Naupaka Zimmerman naupaka@gmail.com
# April 14, 2017

# see:
# https://docs.docker.com/engine/examples/running_ssh_service/
# and
# https://serverfault.com/questions/685697/multiple-commands-in-docker-cmd-directive

# FIXME: root login not working, have to use user rstudio

# build image
docker build -t rstudio-ssh .

# start container from image
docker run -P --name my-rstudio rstudio-ssh

# find port on localhost linked to exposed ports on container (in second terminal) and connect
# docker container ls --all
# ssh -p theport rstudio@localhost
