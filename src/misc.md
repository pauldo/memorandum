# Misc

## Docker

- [Manage Docker as a non-root user](https://docs.docker.com/engine/install/linux-postinstall/)
  1. `sudo groupadd docker`
  1. `sudo usermod -aG docker $USER`
  1. `newgrp docker`
