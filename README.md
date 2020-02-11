# watchtower-docker-compose
### auto updating support for any docker compose'd setup


Hi,
I successfully integrated watchtower into docker compose by specifying containers in the `command` section like this:

```yaml
watchtower:
    image: v2tec/watchtower
    container_name: watchtower
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - /root/.docker/config.json:/config.json
    command: watchtower nginx nginx-gen pma --interval 30
    restart: unless-stopped
```

Like this only the containers `watchtower`, `nginx`, `nginx-gen` and `pma`will be automatically updated.

Cheers


https://github.com/containrrr/watchtower/issues/16
