# dcind-alpine image

(docker-compose-in-docker) alpine docker image containing everyting needed for a unit test step: git, bash, make, docker, docker-compose, etc.

The docker dameon is not started automatically, 
you must first run `start-docker` e.g.
```
docker run --privileged --rm -it dj80hd/dcind-alpine bash -c 'start-docker; docker ps'
```

Or, in concourse
```
  - task: my-task-needing-docker
    config:
      image_resource:
        source:
          repository: dj80hd/dcind-alpine
          tag: latest
          username: ((dockerhub_rw_username))
          password: ((dockerhub_rw_password))
        type: registry-image
      params:
        FOO: bar
      platform: linux
      run:
        path: bash
        args:
        - -c 
        - |
          start-docker
          docker ps
```
