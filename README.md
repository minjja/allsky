docker config create virtualsky.json virtualsky.json
docker config create config.js config.js

docker stack deploy --compose-file docker-stack.yml allsky