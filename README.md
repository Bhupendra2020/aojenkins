aojenkins
=========

Jenkins in a Docker container; based on Ubuntu 13.10. It comes with the
following plugins:

 * hipchat.hpi
 * greenballs.hpi
 * credentials.hpi
 * ssh-credentials.hpi
 * ssh-agent.hpi
 * git-client.hpi
 * git.hpi
 * github.hpi
 * github-api.hpi
 * ghprb.hpi
 * github-oauth.hpi
 * scm-api.hpi
 * postbuild-task.hpi

Usage
-----

    docker run -d -t fnubhupen/aojenkins

Building
--------

Grab Dockerfile from this repository on Github

    docker build github.com/Bhupendra2020/aojenkins

Get a Docker image from Docker index

    docker pull fnubhupen/aojenkins

Run
-------

Run a container using this image and map data directory from the container to the host; e.g in th example below /var/lib/jenkins from the container is mapped to jenkins/ directory from the current path on the host. 
Jenkins 8080 port is also exposed to the host as 49001

Below is pick jenkins folder from $PWD (present working directory)

    docker run -d -p 49001:8080 -v $PWD/jenkins:/var/lib/jenkins -t fnubhupen/aojenkins

Below is when you connect to data only container

    docker run -d -p 49001:8080 --volumes-from <containerName> -t fnubhupen/aojenkins
