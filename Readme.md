# Jenkins in Docker with local Docker registry attached

## Purpose
If you are using Jenkins on your PC, you most likely noticed the time it takes to run first Jenkins job after startup. During this time Docker in Jenkins pulls image specified in Jenkins file. After every Docker dind restart all images used by Jenkins jobs have to be pulled again.  

One of the solutions it to create local Docker registry and get images required for Jenkins build from it.

## You'll need
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

See Jenkinsfile example with local registry usage [here](https://github.com/roman-ks/maze-generator/blob/master/Jenkinsfile)