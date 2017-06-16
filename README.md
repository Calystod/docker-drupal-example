# docker-drupal-example
This is a project example to launch Drupal 8 with Docker

Prerequires
-----------
Before to launch the project for the first time, you need install some composants on your environment.

### On Debian or Ubuntu

* Docker CE
* [Page of installation](https://docs.docker.com/engine/installation/linux/ubuntu/#install-using-the-repository) for Ubuntu
* [Page of installation](https://docs.docker.com/engine/installation/linux/debian/) for Debian
* [Docker-Compose](https://docs.docker.com/compose/install/)

First launch
------------

Welcome in the docker test project. To launch the project for the first time, open your favorite terminal command line and go to the root of this project.
(It is possible to have docker on ConEmu by pressing the dropdown arrow next to the green "+" on the top right, and selecting tools>docker)

Launch:

To up your containers, launch:

```docker-compose up```

If it's your first launch, this command will build your containers too.

Let the `up` run and go in an other tab on your terminal.

To launch command on your environment, you will used the php-cli container. To go in, launch:

`docker-compose run --rm php-cli bash`

If you want, you could add this command in a alias.

When you enter in the php-cli container, you should be to in /var/www/html

Launch the command:
`composer install`

Many things will be install:

* Drupal core
* Drush

You can go on your browser and go to http://127.0.0.1/

Install your new website.

The database informations are:

* Database name = docker_test (-> If you boostrap a new project based on this project, you should to change the value of the environment variable in the .env file)
* Database user=drupal
* Database password=drupal
* Host=db (it's the name of the container which run MariaDB)

and enjoy !

