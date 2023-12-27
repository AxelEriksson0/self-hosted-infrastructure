# Raspberry Pi

I use a Raspberry Pi 4 Model B, 4GB.

## Raspberry Pi Imager

In order to put software on your SD-card I use Raspberry Pi [Imager](https://www.raspberrypi.org/software/).

- I use Ubuntu and use the GDebi Package Installer, otherwise Ubuntu Store might select an older version.
- Raspberry Pi OS Lite (64-bit)
- Control + Shift + X to open advanced menu

  - Set hostname: rxtl.local
  - Enable SSH. Allow public-key authentication only. In my case I had a key under ~/.ssh/id_ed25519.pub
  - If you're running on an older Raspberry Pi, it might not support 5GHz band when configuring the WiFi.

## SSH

```
ssh pi@rxtl.local
```

## Docker

### Install

According to https://docs.docker.com/engine/install/raspberry-pi-os, if using 64-bit OS we should use the installation instructions for https://docs.docker.com/engine/install/debian/.

```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Make sure everything works:

```
sudo docker run hello-world
```

### Configure user group to not need root

```
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```
