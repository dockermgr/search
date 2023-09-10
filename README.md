## 👋 Welcome to search 🚀  

search README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update search
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/search/rootfs"
git clone "https://github.com/dockermgr/search" "$HOME/.local/share/CasjaysDev/dockermgr/search"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/search/rootfs/." "$HOME/.local/share/srv/docker/search/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-search \
--hostname search \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-search/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-search/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/search:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/search
    container_name: casjaysdevdocker-search
    environment:
      - TZ=America/New_York
      - HOSTNAME=search
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-search/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-search/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/search
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/search" "$HOME/Projects/github/casjaysdevdocker/search"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/search"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
