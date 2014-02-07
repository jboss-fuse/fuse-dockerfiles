fabric8-docker
==============

This project builds a [docker](http://docker.io/) container for running [fabric8](http://fabric8.io/)

Try it out
----------

If you have docker installed you should be able to try it out via

    docker run -p 8181 -d -t fabric8/fabric8

If you are on OS X then see [How to use Docker on OS X](DockerOnOSX.md).

e.g. to startup 5 Fabric8 instances; each will get their own IP address etc:

    docker run -d -p 8181 fabric8/fabric8
    docker run -d -p 8181 fabric8/fabric8
    docker run -d -p 8181 fabric8/fabric8
    docker run -d -p 8181 fabric8/fabric8
    docker run -d -p 8181 fabric8/fabric8
    
You can then run **docker attach** or **docker logs** to get the logs at any time.

Run  **docker ps** to see all the running containers or **docker inspect $containerID** to view the IP address and details of a container


Building the docker container locally
-------------------------------------

We have a Docker Index trusted build setup to automatically rebuild the fabric8/fabric8 container whenever the [Dockerfile](https://github.com/fabric8io/fabric8-docker/blob/master/Dockerfile) is updated, so you shouldn't have to rebuild it locally. But if you want to, here's now to do it...

Once you have [installed docker](https://www.docker.io/gettingstarted/#h_installation) you should be able to create the containers via the following:

If you are on OS X then see [How to use Docker on OS X](DockerOnOSX.md).

    git clone git@github.com:fusesource/fabric8-docker.git
    cd fabric8-docker
    ./build

The fabric8 container should then build.

Experimenting
-------------

To spin up a shell in one of the containers try:

    docker run -p 8181 -i -t fabric8:fabric8 /bin/bash

You can then noodle around the container and run stuff & look at files etc.

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/fabric8io/fabric8-dockerfiles/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

