# gitlab-ci-android
GitLab CI image for building Android apps via GitLab CI.
It is available on Docker Hub https://hub.docker.com/u/deanrock/gitlab-ci-android/.

## Build image

```bash
docker build -t deanrock/gitlab-ci-android .
```

If building fail you can debug via where `1b372b1f76f2` is partial build

```bash
docker run --tty --interactive --rm 1b372b1f76f2 /bin/bash
```

## Push build version to repository

```bash
docker push deanrock/gitlab-ci-android
```

## Usage
Change directory to your project directory, than run:

```bash
docker run --tty --interactive --volume=$(pwd):/opt/workspace --workdir=/opt/workspace --rm deanrock/gitlab-ci-android  /bin/sh -c "./gradlew build"
```

## Credit

All credits go to [jangrewe/gitlab-ci-android](https://github.com/jangrewe/gitlab-ci-android) and [appunite/docker](https://github.com/appunite/docker/tree/master/android-java8).
