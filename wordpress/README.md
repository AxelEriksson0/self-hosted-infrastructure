# Wordpress

The `docker-compose.yml` is configured to get a Wordpress site up and running with automatic SSL server certificate via linuxserver/swag. Make sure the URL value is correct and pointing to this server.

If you have no URL you have to comment out the swag configuration and add a port to the wordpress config.

```
docker compose up
```

## Plugins

- Updraft for making backups.
