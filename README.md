# qbittrclone 🚀

Este contenedor contiene el cliente qBittorrent y la herramienta Rclone, con la finalidad de automatizar la subida de nuestras descargas a los principales cloud como gdrive etc.

La forma correcta para lanzar este docker es la siguiente:

```
docker run \
  --name=qbittorrent \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -e UMASK_SET=022 \
  -e WEBUI_PORT=8080 \
  -p 6881:6881 \
  -p 6881:6881/udp \
  -p 8080:8080 \
  -v /tupath/config:/config \
  -v /tupath/downloads:/config/downloads \
  --restart unless-stopped \
-it qbittrclone /bin/bash
```
