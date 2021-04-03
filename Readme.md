1. Create custom dind image  
`docker build dind -t localreg-dind:0.1`
2. Create Jenkins image  
`docker build . -t myjenkins-blueocean:2.0`
3. Run dind and Jenkins
`run_jenkins.bat`