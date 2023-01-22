```
docker pull ghcr.io/minjja/allsky-website
```

```
docker pull ghcr.io/minjja/webdav
```

```
docker secret rm htpasswd
docker run --rm htppd htpasswd -nbB USER PASSWORD | docker secret create htpasswd -
```

```
docker stack rm allsky
```

```
docker stack deploy --compose-file docker-stack.yml allsky
```
