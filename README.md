# docker-compose-files

This is a repository to hold [Docker Compose](https://docs.docker.com/compose/) files I have created.

## Applications

### [ghost](https://github.com/gchan/docker-compose-files/blob/master/ghost/docker-compose.yml)
A multi-container [blogging](https://ghost.org/) application composed of three services (containers):

* Ghost blogging platform using an image configured for Mailgun, [gordonchan/ghost-mailgun](https://github.com/gchan/dockerfiles/tree/master/ghost-mailgun)
* Nginx server using an image configured for Ghost, [gordonchan/nginx-ghost](https://github.com/gchan/dockerfiles/tree/master/nginx-ghost)
* Data volume container using the lightweight [tianon/true](https://hub.docker.com/r/tianon/true/) image

### [spotbot](https://github.com/gchan/docker-compose-files/blob/master/spotbot/docker-compose.yml)
Containers running a Dockerized Ruby script [(gordonchan/spotbot)](https://github.com/gchan/dockerfiles/tree/master/spotbot) to periodically check New Zealand's wholesale electricity prices and tweets when they are high.

The two containers are respectively operating the Twitter handles [nzhay250](https://twitter.com/nzhay250) and [nzhay150](https://twitter.com/nzhay150).

## License

docker-compose-files is Copyright (c) 2015 Gordon Chan and is released under the MIT License. It is free software, and may be redistributed under the terms specified in the LICENSE file.

[![Analytics](https://ga-beacon.appspot.com/UA-70790190-2/docker-compose-files/README.md?flat)](https://github.com/igrigorik/ga-beacon)
