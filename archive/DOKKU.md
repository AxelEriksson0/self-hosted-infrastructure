# Dokku

**Dokku doesn't work with Raspberry Pi, yet! Therefore it's placed in archive**

**There's support for armhf but not arm64 yet - https://dokku.github.io/release/dokku-0.26.0, https://github.com/dokku/dokku/pull/4975**

## Install Dokku

### Use via Docker

```
docker pull dokku/dokku:latest
```

```
docker run \
  --env DOKKU_HOSTNAME=dokku.me \
  --name dokku \
  --publish 3022:22 \
  --publish 8080:80 \
  --publish 8443:443 \
  --volume /var/lib/dokku:/mnt/dokku \
  --volume /var/run/docker.sock:/var/run/docker.sock \
  dokku/dokku:latest
```

To enter the Dokku Docker container:

```
docker exec -it dokku bash
```

### Install via Debian

Install Dokku via apt-get

```
wget https://raw.githubusercontent.com/dokku/dokku/v0.26.6/bootstrap.sh; \
sudo DOKKU_TAG=v0.26.6 bash bootstrap.sh
```
