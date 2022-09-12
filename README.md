docker stack rm allsky

docker config rm virtualsky.json config.js
docker config create virtualsky.json virtualsky.json
docker config create config.js config.js

docker stack deploy --compose-file docker-stack.yml allsky