# Misc

## Docker

- [Manage Docker as a non-root user](https://docs.docker.com/engine/install/linux-postinstall/)
  1. `sudo groupadd docker`
  1. `sudo usermod -aG docker $USER`
  1. `newgrp docker`

- Linux
  - netstat 显示监听端口命令
    1. 安装 net-tools
    1. `sudo netstat -tulnp`
      - -t: tcp
      - -u: udp
      - -l: listening
      - -n: not show port number
      - -p: port (need root permission)

  - date 日期转换
    1. `date +%Y%m%d%H%M%S -d @1234567890`
    1. `date +%s -d "2020-01-01 00:00:00"`

  - git 免密拉取代码
    `git config --global credential.helper store`
