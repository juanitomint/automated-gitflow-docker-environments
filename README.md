# automated-gitflow-docker-environments
Orchestation solution for automated gitflow matching environments
The goal is to have an environment to run test & show every stage of the git-flow
So wvery time a new branch, feature, hotfix or release is created in the main repository a Docker environment is created for that branch.
Then you will have a complete environment based on a docker-compose
ie: http://feature_buttons.your.domain.me 
where feature_buttons is the name of the feature you are developing

Moving Parts:
1 docker & docker-compose

2 A GIT repository with a docker-compose.yml and helper files (configs, assets, etc) needed to create an environment

3 A GIT server with webhooks: github, gitlab, or any other: this server will fire the events to listen daemons to create update or destroy the environments

4 A Daemon or web app listening to webhooks events. This app will convert events to actions to Create Update Destroy environments for any new or existing branch

5 A BASH Script for Create Update & Destroy environments based on point 2

6 A reverse proxy NGINX with docker virtual hosts.
6.1 * Optional:  a DNS Gen capable of mapping VIRTUALHOST environment variable
7 OPTIONAL a local docker registry proxy caché.
8 OPTIONAL a local apt package caché apt-catcher
