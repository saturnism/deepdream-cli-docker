Deep Dream Container
====================

This is an example Deep Dream container that runs https://github.com/google/deepdream in command line mode.

This example assumes you know how to run Docker.

This is not an official Google product.

Running the Container
---------------------
To run this container:

    $ docker run -i saturnism/deepdream-cli -h
    $ cat myimage.jpg | docker run -i saturnism/deepdream-cli > output.jpg
    $ cat myimage.jpg | docker run -i saturnism/deepdream-cli -l conv2/3x3 > output.jpg

