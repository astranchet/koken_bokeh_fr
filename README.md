
## Run locally

### Installation

```sh
docker pull koken/koken-lemp
mkdir -p /data/koken/www
mkdir -p /data/koken/mysql
```

```sh
CID=$(docker run --restart=always -p 4444:8080 -v /data/koken/www:/usr/share/nginx/www -v /data/koken/mysql:/var/lib/mysql -d koken/koken-lemp /sbin/my_init)
IP=$(docker inspect $CID | grep IPAddress | cut -d '"' -f 4)
echo "Go to: http://$IP"
```

