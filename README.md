Deep Dream Container
====================

This is an example Deep Dream container that runs https://github.com/google/deepdream in command line mode.

This example assumes you know how to run Docker.

This is not an official Google product.

Building the Container
----------------------
Nothing special if you already have Docker installed:

    $ git clone https://github.com/saturnism/deepdream-cli-docker.git
    $ cd deepdream-cli-docker
    $ docker build -t deepdream-cli .

Running the Container
---------------------
To run this container:

    $ cat myimage.jpg | docker run -i deepdream-cli > output.jpg
    $ cat myimage.jpg | docker run -i deepdream-cli /deepdream/deepdream.py -l conv2/3x3 > output.jpg
    
To see all of the available arguments:

    $ docker run -i deepdream-cli /deepdream/deepdream.py -h

Running in the Background
-------------------------
Rather than waiting for the images to be outputed to STDOUT, you can also pipe the image to the container filesystem and get it later:

    $ cat myimage.jpg | docker run -i deepdream-cli /bin/bash -c "/deepdream/deepdream.py > /tmp/output.jpg" &
    
Find the container ID:

    $ docker ps

Or, if the container already exited:

    $ docker ps -a | less

When the container process finishes, you can copy the image out:

    $ docker cp containerId:/tmp/output.jpg .
