# Raspberry Pi

I use a Raspberry Pi 4 Model B, 4GB.

## Raspberry Pi Imager

- Download [Imager](https://www.raspberrypi.org/software/)
- Raspberry Pi OS Lite (64-bit)
- Control + Shift + X to open advanced menu

  - Set hostname: axle.local
  - Enable SSH. Allow public-key authentication only. In my case I had a key under ~/.ssh/id_ed25519.pub
  - If you're running on an older Raspberry Pi, it might not support 5GHz band when configuring the WiFi.

## SSH

```
ssh pi@axle.local
```

## Docker

### Install

```
sudo apt-get update && sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

### Configure user group to not need root

```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```
