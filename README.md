# autojenkins
Jenkins + docker automatic set up

This repository contains experiments to automatically set up a jenkins master + slave.

# How to use

TBD


# How this works

Generate plugin list with fixed versions from an existing installation:
```
curl -s -k "http://admin:admin@localhost:8080/pluginManager/api/json?depth=1" \
  | jq -r '.plugins[] | .shortName+":"+.version' | tee plugins.txt
```

# References
- https://technologyconversations.com/2017/06/16/automating-jenkins-docker-setup/
- https://github.com/michaellihs/jenkins-swarm
