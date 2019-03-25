---
title: Backstop JS and Lando
author: Stephen Cross
tags:
    - Drupal
list_image: /images/blog/backstop-lando-listing.jpg
list_image_alt: Backstop and Lando
primary_image: /images/blog/backstop-lando-primary.jpg
primary_image_alt: Backstop and Lando
---
I've recently started using [Backstop JS](https://github.com/garris/BackstopJS) for visual regression testing.  You can add the following settings to your [Lando](https://docs.devwithlando.io) configuration, .lando.yml,  to include Backstop JS.

```
services:
  node:
    type: node:10
    globals:
      backstopjs: "latest"
    command: npm start
    run_as_root:
      - apt-get -y update && apt-get -y install software-properties-common
      - wget https://dl-ssl.google.com/linux/linux_signing_key.pub && apt-key add linux_signing_key.pub
      - add-apt-repository "deb http://dl.google.com/linux/chrome/deb/ stable main"
      - apt-get -y update && apt-get -y install google-chrome-stable
tooling:
  backstop:
    service: node
```

You will need to use the .internal URL from Lando to access the local website.  For example:

```
  "scenarios": [
    {
      "label": "Homepage",
      "url": "http://appserver_nginx.your-site-name.internal"
    }
```

The backstop commands will be run through Lando tooling:

```
lando backstop reference
lando backstop test
```


-S
