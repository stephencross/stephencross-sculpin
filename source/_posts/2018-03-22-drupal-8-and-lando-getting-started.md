---
title: Drupal 8 and Lando - Getting Started
author: Stephen Cross
tags:
    - Drupal
---
This is a quick guide for installing Drupal 8 on your local computer with composer and running it on Lando.

## Pre-requisites
You will need composer, docker and Lando installed first.   I've used the same basic steps to get configuration running on Mac and Linux. Windows is also available.

Lando - [https://docs.devwithlando.io/installation/installing.html](https://docs.devwithlando.io/installation/installing.html)

Composer - [https://getcomposer.org/doc/00-intro.md](https://getcomposer.org/doc/00-intro.md)

Docker - [https://docs.docker.com/docker-for-mac/](https://docs.docker.com/docker-for-mac/)

## Installation Directory
The steps below are for installing Drupal 8 into the ~/Documents/dev/lando/d85 folder on my Mac.  Substitute the locations are you see fit.

## Setup Software Stack
If you have installed the pre-requisites, you can follow these steps to get the software stack running.   Position yourself in the parent directory of where the application should be installed. In my case, ~/Documents/dev/lando.

```shell
cd ~/Documents/dev/lando
```

Drupal will be installed with the drupal-composer project. To learn more about drupal-composer see reference section below. Replace the ‘d85’ with your application directory name.

```shell
composer create-project drupal-composer/drupal-project:8.x-dev d85  --stability dev --no-interaction
```

The Drupal code has been installed. Position your in the newly created application directory.

```shell
cd ~/Documents/dev/lando/d85
```

We will now create a Lando instance using a Drupal 8 recipe. You will be asked two questions. 1. Webroot - Your webroot is ‘web’, drupal-composer is setup to make the folder the webfoot. 2. App name - I like to make the app name and folder the same.

```shell
lando init --recipe drupal8
Where is your webroot relative to the init destination? (.) web
What do you want to call this app? (My Lando App) d85
```

The lando init process is quick, it creates a .lando.yml file. The next step is to build the Lando instance. When complete, Lando will provide you with a URL to the newly created Drupal website. My URL was http://localhost:32828

```shell
lando start
```

## Install Drupal

Using the link provided, you will see the Drupal install page.

**Choose Language:** - Leave default, Save and Continue

**Choose Profile:** - Leave default, Save and Continue

**Setup Database:** Use the information below for the database settings, use the Advanced button to set the proper Host Name to 'database'.

```shell
DB_HOST=database DB_USER=drupal8 DB_PASSWORD=drupal8 DB_NAME=drupal8 DB_PORT=3306
```

**Configure Site:** Provide all the required information.

**DONE.**


## Lando Commands
I found the following commands useful.

```shell
lando - will provide summary of the lando commands you have access to.

lando poweroff - to shutdown this lando instance

lando start - to start the lando instance

lando destroy - to delete the instance

lando info - display configuration information

lando drush - access to drush commands
```

## Resources
[Lando](https://docs.devwithlando.io/)

[Lando Drupal 8 Documentation](https://docs.devwithlando.io/tutorials/drupal8.htm)

[System Requirements for Lando](https://docs.devwithlando.io/installation/system-requirements.html)

[Docker](https://www.docker.com/)

[Using Composer with Drupal](https://www.drupal.org/docs/develop/using-composer/using-composer-with-drupal)

[Drupal Composer](https://github.com/drupal-composer/drupal-project)