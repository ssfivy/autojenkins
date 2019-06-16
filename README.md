# autojenkins
Jenkins + docker automatic set up

This repository contains experiments to automatically set up a jenkins master + slave.

Work in progress, do not take as exanple.

# How to use

# OS preparation
- Install docker

## Preparing secrets
For now, create a password.secret and username.secret file.
Might figure out better scheme later.

## Building and Starting container

```
docker-compose up
```

# How this works

Generate plugin list with fixed versions from an existing installation:
```
curl -s -k "http://admin:admin@localhost:8080/pluginManager/api/json?depth=1" \
  | jq -r '.plugins[] | .shortName+":"+.version' | tee plugins.txt
```

# References
- https://technologyconversations.com/2017/06/16/automating-jenkins-docker-setup/
- https://github.com/michaellihs/jenkins-swarm
- https://hub.docker.com/pricing
- https://blog.alexellis.io/jenkins-meets-the-proxy/
