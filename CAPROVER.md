# CapRover

[CapRover](https://caprover.com/) is an open-source self-hosted PaaS. The reason I chose it is because it works on a Raspberry Pi.

1. Get the image

```
docker pull caprover/caprover
```

2. Install ufw (uncomplicated firewall). Allows opening ports needed for Caprover.

```
sudo apt-get install ufw
```

```
sudo ufw allow 80,443,3000,996,7946,4789,2377/tcp; ufw allow 7946,4789,2377/udp;
```

3. Start Caprover.

```
mkdir /captain
```

```
docker run --name caprover -p 80:80 -p 443:443 -p 3000:3000 -e MAIN_NODE_IP_ADDRESS=127.0.0.1 -e DEFAULT_PASSWORD=custom_default_password -v /var/run/docker.sock:/var/run/docker.sock caprover/caprover
```

Notice the `DEFAULT_PASSWORD` variable.

4. Now it should be accessible on `http://127.0.0.1:3000`.

5. Install nvm

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

Automatically source it with the command returned so you don't need to restart the terminal.

```
nvm install --lts
```

```
npm i -g caprover
```

6. Caprover setup.

```
caprover serversetup
```

## GitHub

When connecting the repository to CapRover, need to connect with RSA key and not OPENSSH. I created a new keypair to get it working.

## Troubleshooting

```
docker swarm leave
```
