# Docker

## Docker without sudo 

```shell
sudo groupadd docker
sudo gpasswd -a `whoami` docker
sudo service docker restart
newgrp - docker
```
