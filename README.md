```sh
docker config rm config.js
docker config create config.js etc/config.js
```

```sh
docker secret rm virtual_users.txt
printf "user\password" | docker secret create virtual_users.txt -
```

```sh
docker pull fauria/vsftpd
docker pull ghcr.io/minjja/allsky-website:latest
```

```sh
docker stack rm allsky
```

```sh
docker stack deploy --compose-file docker-stack.yml allsky
```
