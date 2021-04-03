## You'll need:
* local Docker registry. See [Docker docs](https://docs.docker.com/registry/deploying/)

## To start Jenkins in Docker with local registry

1. Create custom dind image  
`docker build dind -t localreg-dind:0.1`
2. Create Jenkins image  
`docker build . -t myjenkins-blueocean:2.0`
3. Run dind and Jenkins
`run_jenkins.bat`
4. Add local registry to the Docker network  
`docker network connect --alias myregistry jenkins registry`