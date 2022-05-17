# linuxserver-io-mod-qbit-matui

[qbit-matUI](https://github.com/bill-ahmed/qbit-matUI) theme mod for LinuxServer.io's qBittorrent container

## Usage

1. Add an environment variable called `DOCKER_MODS` with the value `marzzzello/linuxserver-io-mod-qbit-matui` when creating the container.

Example: `docker-compose.yml`

```yml
---
qbittorrent:
  image: linuxserver/qbittorrent
  container_name: qbittorrent
  environment:
    - PUID=1000
    - PGID=1000
    - UMASK=022
    - WEBUI_PORT=9090
    - DOCKER_MODS=marzzzello/linuxserver-io-mod-qbit-matui
  volumes:
    - ./data/qbittorrent:/config
    - /home/user/Downloads:/downloads
  ports:
    - 6881:6881
    - 6881:6881/udp
    - 9090:9090
  restart: unless-stopped
```

2. Go to Settings -> WEBUI, check `Use alternative Web UI` and enter its location `/qbit-matui`, then save.
   <img src="https://user-images.githubusercontent.com/15198431/168888606-e5c42f88-30e1-48f2-b43e-2ab98807df96.png" />

## Sources

- [linuxserver-io-mod-vuetorrent](https://github.com/arafatamim/linuxserver-io-mod-vuetorrent)
- [qbit-matUI repo](https://github.com/bill-ahmed/qbit-matUI)
- [LinuxServer's qBittorrent on Docker Hub](https://hub.docker.com/r/linuxserver/qbittorrent)
