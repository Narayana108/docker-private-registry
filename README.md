# Docker Private Registry with TLS and Basic AUTH

## Requirements:
1. Generate ssl certs in ./nginx/ssl/
```bash
openssl req -new -newkey rsa:2048 -days 365 -nodes -x509 -keyout \
docker.krsna.net.key -out docker.krsna.net.crt
```

2. Generate htpasswd 
```sh
docker run --entrypoint htpasswd   registry:2 -Bbn dockerreg dockerreg > \
auth/registry.passwd
```

## Start
`docker-compore up`
