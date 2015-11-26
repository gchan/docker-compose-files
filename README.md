# docker-compose-files

This is a repository to hold [Docker Compose](https://docs.docker.com/compose/) files I have created.

## Applications

### [ghost](https://github.com/gchan/docker-compose-files/blob/master/ghost/docker-compose.yml)
A multi-container [blogging](https://ghost.org/) application composed of three services (containers):

* Ghost blogging platform using an image configured for Mailgun, [gordonchan/ghost-mailgun](https://github.com/gchan/dockerfiles/tree/master/ghost-mailgun)
* Nginx server using an image configured for Ghost, [gordonchan/nginx-ghost](https://github.com/gchan/dockerfiles/tree/master/nginx-ghost)
* Data volume container using the lightweight [tianon/true](https://hub.docker.com/r/tianon/true/) image

## License

docker-compose-files is Copyright (c) 2015 Gordon Chan and is released under the MIT License. It is free software, and may be redistributed under the terms specified in the LICENSE file.
