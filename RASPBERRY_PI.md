# Raspberry Pi

I use a Raspberry Pi 4 Model B, 4GB.

## Raspberry Pi Imager

- Download [Imager](https://www.raspberrypi.org/software/)
- Control + Shift + X to open advanced menu

- Raspberry Pi OS Lite (32-bit)
- Set hostname: axle.local
- Enable SSH. In my case I had a key under ~/.ssh/id_ed25519.pub

WiFi configuration (!)

- If you're running on an older Raspberry Pi it might not support 5GHz band.

## SSH

```
ssh pi@axle.local
```

## Install Docker

```
sudo apt-get update && sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
