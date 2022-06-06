# balena Portainer block

This is a block that can be used to run Portainer on a Raspberry Pi and get all the benefits of running Portainer and balena along.

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
      - data:/data
volumes:
  data:
```

## Test Portainer on balena

If you would like to test a standalone version, click the button below

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/mpous/balena-portainer)

and deploy the code into a balenaCloud fleet. 

Once you flashed a SD card with the balenaOS image from that fleet you will be able to see this:

<img width="1904" alt="portainer-balenaCloud" src="https://user-images.githubusercontent.com/173156/170042835-5c6cc5aa-a803-4bed-8c01-6f66d3225bd6.png">

Type on the browser `https://<local ip address>:9433` and you might be able to access to the Portainer UI.

<img width="1904" alt="portainer-balena" src="https://user-images.githubusercontent.com/173156/170043014-e79625df-b683-4e9f-b090-76abfc657c5d.png">

Click `Add Environment` to start using Portainer on balena.

![Add Environment on Portainer on balena](https://user-images.githubusercontent.com/173156/172139253-b2a062b4-ed02-4d90-a7e8-c6caca70cf45.png)

Now select `Docker`and click `Connect via socket` plus `Override default socket path`. You are going to be able to use the `balena-engine` sock to connect with the Portainer Docker API. Add the public IP of your device as well.

![Configure your Docker environment on Portainer on balena](https://user-images.githubusercontent.com/173156/172139561-5880491d-a840-4330-affb-cd37c730f5bd.png)

As a result, you might have a new environment on your device.

![Portainer environment list on balena](https://user-images.githubusercontent.com/173156/172139622-7f6140d0-647d-4ec5-a326-291ffa316aa6.png)

From now you can start adding new containers on your Portainer running balena.

![Containers running on Portainer on balena](https://user-images.githubusercontent.com/173156/172139719-0f674321-4d75-4e5f-8d1d-df39cc1eab3c.png)

Have fun and let us know what you deployed with Portainer on balena please :)


## Contributing

Do you want to help make the balena Portainer example better? Feel free to contribute opening issues and PRs.

## Acknowledgement

Thanks [@klutchell](https://github.com/klutchell) for setting up the docker-compose for building portainer using balena.
