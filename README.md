# balena Portainer block

This is a block that can be used to run Portainer on a Raspberry Pi and get all the benefits of running Portainer and balena along.

## Setup and configuration

Use this as standalone with the button below

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/balena-portainer)

Or add the following service to your `docker-compose.yml`:

```
services:
  portainer:
    image: portainer/portainer-ce:latest
    ports:
      - 9000:9000
      - 9443:9443
    labels:
      - io.balena.features.balena-socket=1
    volumes:
      - data:/data
volumes:
  data:
```

## Getting Help

If you're having any problem, please raise an issue on GitHub and we will be happy to help.

## Contributing

Do you want to help make the balena Portainer example better? Feel free to contribute opening issues and PRs.
