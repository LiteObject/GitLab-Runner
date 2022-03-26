## How to Setup GitLab Runner Locally
- Run gitlab-runner in docker container
  - $ `docker-compose up -d`  
- Go inside the container to run bash command
  - $ `docker exec -it <CONTAINER_ID> bash`
- To update & upgrade
  - $ `apt-get update`
  - $ `apt-get upgrade`
- To register gitlab runner
  - Information required for runner registration is available here:
    - Settings -> CI / CD -> Runners -> Specific Runners -> Set up a specific Runner manually
  - $ `gitlab-runner register`
    - Enter the GitLab instance URL (for example, https://gitlab.com/): http://gitlab.xxx.xxxxx.com/
    - Enter the registration token: Rbjsjghmjy_Ygdfgt7xz
    - Enter a description for the runner: my-local-gitlab-runner
    - Enter tags for the runner (comma-separated): local,my-runner
    - Enter optional maintenance note for the runner: none
- If the runner is not working, then make sure, the token inside (etc -> gitlab-runner -> config.toml) has the correct token
- To see all running GitLab runners:
  - $ `gitlab-runner list`
- To stop, start and restarting runner
  - $ `gitlab-runner stop`
  - $ `gitlab-runner start`
  - $ `gitlab-runner restart`
-To view logs of the runner container
  - $ `docker logs --tail 1000 -f <CONTAIER_ID>`

## How to Install .NET SDK on Linux
- $ `wget https://packages.microsoft.com/config/ubuntu/21.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb`
- $ `dpkg -i packages-microsoft-prod.deb`
- $ `rm packages-microsoft-prod.deb` (optional)
- $ `apt-get update`
- $ `apt-get install -y apt-transport-https`
- $ `apt-get update`
- $ `apt-get install dotnet-sdk-6.0`
- $ `dotnet --version`

## How to Install EF Core on Linux
- $ `export PATH=$PATH:/root/.dotnet/tools`
- $ `dotnet tool install --global dotnet-ef`