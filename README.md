# balena Portainer block

This is a block that can be used to run Portainer on a Raspberry Pi and get all the benefits of running Portainer and balena together.

## Add Portainer into your balena fleet

Add the following service to your `docker-compose.yml`:

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
      - portainer_data:/data
    command: -H unix:///var/run/balena-engine.sock
volumes:
  portainer_data:
```

## Test Portainer on balena

If you would like to test a standalone version, click the button below

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/balena-portainer)

and deploy the code into a balenaCloud fleet.

Once you flashed a SD card with the balenaOS image from that fleet you will be able to see this:

<img width="1904" alt="portainer-balenaCloud" src="https://user-images.githubusercontent.com/173156/170042835-5c6cc5aa-a803-4bed-8c01-6f66d3225bd6.png">

Type in your browser `http://<local ip address>:9000` and you will be able to access the Portainer UI.

<img width="751" alt="2022-06-02 at 09 08 39" src="https://user-images.githubusercontent.com/64841595/171585754-c86a9afa-2d93-402c-85a3-4f482881f3d1.png">

## Contributing

Do you want to help make the balena Portainer example better? Feel free to contribute opening issues and PRs.

## Acknowledgement

Thanks [@klutchell](https://github.com/klutchell) for setting up the docker-compose for building portainer using balena.
