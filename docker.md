# Docker

## Commands

- `docker ps` list running image instances
- `docker ps -a` list all image instances
- `docker images` list available images
- `docker rm <instance id>`
- `docker restart <image name>` restarts an existing named image.


### Docker run
- `docker run <image|image-name>`
- `-it` is interactive mode
- `-d` dettached from terminal
- `-p 80:80` port mapping

### Volume mapping

`docker run -v /opt/datadir:/var/lib/mysql mysql` maps the local folder to the container folder to persist data in your computer
