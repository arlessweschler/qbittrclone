# qbittrclone 🚀

Este contenedor de docker contiene el cliente qBittorrent y la herramienta Rclone, con la finalidad de automatizar la subida de nuestras descargas a los principales servidores cloud como gdrive etc.

### Pre-requisitos 📋
Únicamente necesitaremos tener docker instalado en nuestro sistema operativo.

## Despliegue 📦
La forma más recomendades para lanzar este contenedor es la siguiente:

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
## +info 📖
La versión que contiene del cliente qBittorrent es la v4.2.1
