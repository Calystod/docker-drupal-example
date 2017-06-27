# docker-drupal-example
This is a project example to launch Drupal 8 with Docker

First information
-----------------

This project has for goal to present simply how to create a docker environment to people which have never work with
Docker. This project is concentrate on Drupal specifically but can be adapt to work with other technologies.

You find documentation links and commentaries. If you want complete or correct errors, you can fork this project and do
a pull request.

To know how to assign a static IP to containers, you can checkout the branch docker-networks. But this branch is in
work in progress and this methology isn't recommand except if we want access to container on external networks.

Prerequires
-----------
Before to launch the project for the first time, you need install some composants on your environment.

### On Debian or Ubuntu

* Docker CE

For Linux:
* [Page of installation](https://docs.docker.com/engine/installation/linux/ubuntu/#install-using-the-repository) for Ubuntu
* [Page of installation](https://docs.docker.com/engine/installation/linux/debian/) for Debian
* [Docker-Compose](https://docs.docker.com/compose/install/)

For Mac OS:
* [Page of installation](https://docs.docker.com/docker-for-mac/install/)
 
For Windows:
* [Page of installation](https://docs.docker.com/docker-for-windows/install/#download-docker-for-windows)

> **Important**: Docker on Linux doesn't work exactly in the same way than on Mac OS and Windows. On these two last
> environments, Docker works with the Docker Toolbox. It's an application which contain all elements necessary for Docker
> together with the Docker Machine and some experimental features enabled by default.
>
> This project is realized on Linux, so the documentation could be uncompleted or wrong for Mac OS and Windows.

First launch
------------

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

> Warning: This is true on Linux, not on Windows Home where you must connect to the IP of the VirtualBox machine which run. It is to see on Mac OS and Windows Pro.

Install your new website.

The database informations are:

* Database name = docker_test (-> If you boostrap a new project based on this project, you should to change the value of the environment variable in the .env file)
* Database user=drupal
* Database password=drupal
* Host=db (it's the name of the container which run MariaDB)

You can go on phpMyAdmin with [http://127.0.0.1:8080/](http://127.0.0.1:8080/)

Other informations:

In the file .env, the USER_UID must match with the USER_UID of your personnal user to have the same right.

Verify your user id with the command:
`id -u`

and change the data in the .env if necessary. You can used an utility like [direnv](https://direnv.net/) or a global variable.

and enjoy !

Documentation
-------------

* [What is Docker?](https://www.docker.com/what-docker)
* [Docker Documentation](https://docs.docker.com/)
* [Docker Compose V2 - File references](https://docs.docker.com/compose/compose-file/compose-file-v2/)
* [PHP Image of Docker](https://hub.docker.com/_/php/) -> Important to understand how to active php extensions in containers and other things. DrupalDocker PHP image is based on it.