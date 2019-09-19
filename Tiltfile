# -*- mode: Python -*-

compose_files = [

  './docker-compose.myServiceA.yml',
  './docker-compose.myServiceB.yml',

]

## Service B

docker_build('mysuperimage', './myServiceB/', dockerfile='./myServiceB/Dockerfile.dev',
  live_update = [
    sync('./myServiceB/src', '/usr/src/app/src'),
    run('npm i', trigger='./myServiceB/package.json'),
    restart_container()
  ])

docker_compose(compose_files)
