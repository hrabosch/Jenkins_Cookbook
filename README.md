# Jenkins Cookbook

## Local environement for CI/CD

In _Env_ directory is located docker-compose file with following services:

- **Jenkins** To run our pipelines and do a job done. [Official website](https://www.jenkins.io/)
- **Gitea** Gitea to get some UI for Git itself. [Official website](https://gitea.io/en-us/)

### Quick start of local self-hosted Git and Jenkins

Run `docker-compose.ylm` file within _env_ folder. Pay attention to configured **data volumes** for Jenkins and Gitea to persist a data after stopping running containers.

**Jenkins** is configured to run without installation wizard and with default administrator user.

- Run Jenkins in docker without installation wizard by adding `-Djenkins.install.runSetupWizard=false` to **JAVA_OPTS**
- Run Jenkins in docker with default administrator username/password by adding `--argumentsRealm.roles.user=USERNAME --argumentsRealm.passwd.admin=PASSWORD --argumentsRealm.roles.admin=admin` into **JENKINS_OPTS**

> Jenkins will be without any additional plugins. Install plugins based on your needs or enable _Setup wizard_. In that case, for first login use a password stored in **env/jenkins-data/secrets/initialAdminPassword**.

**Gitea** has already predefined **app.ini** file in **env/gitea-data/gitea/conf/**. If you need to expose and use different host defined in compose file, do not forget to change that port in this file or later on via web UI of Gitea in Settings.

> Gitea fresh installation **_DOES NOT_** have a **_default administrator or user account_**. After first start, register your desired user which will be administrator by default.

# What else?

Finish Readme! As always..
