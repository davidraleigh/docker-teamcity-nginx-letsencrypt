# docker-teamcity-nginx-letsencrypt
 Dockerized TeamCity with SSL support using nginx and letsencrypt

# Requirements

Docker and docker-compose:
* https://docs.docker.com/engine/installation/
* https://docs.docker.com/compose/install/

# Usage

Your domain `yourfancyurlname.com,www.yourfancyurlname.com` needs to be publicly resolvable and accessible from the internet.

Modify the domain and e-mail address inside the `.env` file:

```
VIRTUAL_HOST_LIST=yourfancyurlname.com,www.yourfancyurlname.com
LETSENCRYPT_HOST_LIST=yourfancyurlname.com,www.yourfancyurlname.com
LETSENCRYPT_EMAIL=BoatyMcBoatFace@yourfancyurlname.com
TEAMCITY_DIR=/path/to/your/teamcity_data
```

Bring up the services:

```
docker-compose up
```

Access your teamcity server on: https://yourfancyurlname.com
Note that on the first run it could take few minutes to initialise the Let's Encrypt.


References:
* https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion
* https://github.com/jwilder/nginx-proxy
* https://github.com/dataminelab/docker-jenkins-nginx-letsencrypt
* https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion/issues/277
* https://confluence.jetbrains.com/pages/viewpage.action?pageId=74845225#HowTo...-NGINX
* https://hub.docker.com/r/jetbrains/teamcity-server/
* https://confluence.jetbrains.com/display/TCD10/Using+HTTPS+to+access+TeamCity+server
