Table of Contents
=================

   * [Introduction](#introduction)
   * [Building image](#building-image)
   * [Exposed volumes](#exposed-volumes)
   * [Usage](#usage)

# Introduction
Docker image used to build projects with [gradle](https://gradle.org). Similar to [maven](https://hub.docker.com/_/maven/).

# Building image
Clone this repository and then run:
```
> docker build -t alpine-gradle .
```

# Exposed volumes

* /work : Main directory where gradle works from.
* /GRADLE_CACHE : Gradle cache directory.
  If not set, it will cause gradle to re-download libraries on every iteration. If set to a local host directory it will speed up subsequent builds.

# Usage
Go to the base directory of your gradle project and run:
```
> docker run  -v $PWD:/work -v $PWD/.gradle:/GRADLE_CACHE hipposareevil/alpine-gradle --version
```

