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

  - Useful commands
    - `zoxide`
      - `zoxide init zsh >> ~/.zshrc_local && source ~/.zshrc_local` # init
      - `z some path`
    - `pass`
      - `gpg --full-generate-key` # input user eg. paul, or `gpg --import /path/to/keyfile` if you already have a key
      - `pass init paul`
      - `pass insert website/username`
      - `pass -c website/username`
    - `jq`
    - `sq`
      - `sq completion zsh >> ~/.zshrc_local && source ~/.zshrc_local`
      - `sq add mysql://xxx`
      - `sq ls`
      - `sq src @xxx`
      - `sq '.user | ob(.id-) | .[0:5] | .user_id, .nickname'`
    - `fzf`
    - `fd`
    - `ripgrep`

  - nginx 跨域配置
    - ```
    ```
    add_header Access-Control-Allow-Origin "*";
    add_header Access-Control-Allow-Methods "*";
    add_header Access-Control-Allow-Headers "*";
    if ($request_method = 'OPTIONS') {
      return 204;
    }
    ```
    ```
    if ($request_method = 'OPTIONS') {
      add_header 'Access-Control-Allow-Origin' '*';
      add_header 'Access-Control-Allow-Credentials' 'true';
      add_header 'Access-Control-Allow-Headers' 'Authorization,Accept,Origin,DNT,X-CustomHeader,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Content-Range,Range';
      add_header 'Access-Control-Allow-Methods' 'GET,POST,OPTIONS,PUT,DELETE,PATCH';
      add_header 'Access-Control-Max-Age' 1728000;
      add_header 'Content-Type' 'text/plain charset=UTF-8';
      add_header 'Content-Length' 0;
      return 204;
    }
    proxy_redirect off;
    ```

  - brew php old version
    - `brew tap shivammathur/php`
    - `brew tap shivammathur/extensions`
    - `brew install shivammathur/php/php@7.4`

  - openssl check password
    - `echo "123456" | openssl pkcs12 -in payer61.pfx -info -nokeys -passin stdin`

  - install php redis extension
    - ```
      git clone https://www.github.com/phpredis/phpredis.git
      cd phpredis
      phpize && ./configure && make && sudo make install
      ```

  - mac: xxx dmg is damaged and can’t be opened
    - sudo xattr -rd com.apple.quarantine $xxx # 可拖拽到命令行


