# apify-actor-docker

Public Docker images for the Apifier Actor runtime (https://www.apifier.com)

The sources for the images are present in subdirectories that are named as the corresponding
Docker image. For example, the `default` directory corresponds to the
[apify/actor-default](https://hub.docker.com/r/apify/actor-default/) Docker image.

The images are using the following tags:

Tag         | Description
----------- | -------------
`latest`    | Well-tested production version of the image.
`beta`      | Development version of the image.


## Maintenance

In order to build and publish a new version of the Docker images,
first ensure you're logged in to your Docker Hub account by running:

```bash
docker login
````

Then build the Docker image:

```bash
./build.sh node-basic
```

After the Docker image is well tested, it can be pushed with the `latest` tag:

```bash
docker push apify/actor-node-basic:latest
```

Then you can remove the images from your computer:
```bash
./clean.sh
```

*IMPORTANT*

If the `beta` images were built by Travis CI and are already available on Docker Hub
but not your local computer, then to publish them with the `latest` you need to
run the following script:

```bash
./publish_beta_as_latest.sh node-basic
```

Do the same for other images,

**TODO: Setup Circle CI to do this automatically on commit, development branch corresponds to beta, master to latest**
