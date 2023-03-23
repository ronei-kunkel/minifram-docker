# Docker to php mysql and nginx project

Mounted to set up infrastructure for php projects using the minifram php framework <https://github.com/ronei-kunkel/minifram-php>.
Principal feature is persist volume of mysql. This feature enable mantain data of your project intact when you stop the containers. Obviously, its a feature to make more easly the development than deploy, but its a interesting feature.
The second feature is support to multi projects with web and api interface. If you need make project of service to do a little bit of business rule and make the principal project you do. If you need make an api to have a way to third part modify data and make a web interface to user interact to project you do too.

## Images

- php:8.2-fpm
- nginx:1.18.0-alpine like
- mysql:8.0.32

## How to

In priori, (not tested yet) you only need do these steps:

1. Clone this project into anywhere you want.

2. Into cloned folder run `docker-compose build && docker-compose up -d`.

3. After building and set up the containers, the infra is done.

4. After infra finish the setup, go to 'projects' folder and clone the minifram framework <https://github.com/ronei-kunkel/minifram-php> (documentation in progress) into folder.

5. When clone finished, rename the framework folder with what you want.

6. After rename, just go to <http://localhost/{folder-name}/> to access the web interface of project and <http://localhost/{folder-name}/api/> to access the api interface of project.

7. If you need or if you want, repeat from 4 step to 6 step to set up more projects with the framework.
