An attempt at making a portable ANTsR docker app, with some
visualization capabilities via RStudio and GPU support.

Based on: https://hub.docker.com/r/rocker/ml

See the dockerfile to get the specific version - eg rocker/ml:4.0.2-cuda10.1

or rocker/ml:4.0.0-cuda10.2-ubuntu18.04

**Note: gpu images require nvidia-docker** runtime to run!

Run a bash shell or R command line:

```
docker run --rm -ti stnava/antsxdockergpu:latest /bin/bash
nvidia-docker run --rm -ti stnava/antsxdockergpu:latest /bin/bash
```

Or run in RStudio instance:

```
docker run -e PASSWORD=mu -p 8787:8787 stnava/antsxdockergpu:latest
nvidia-docker run -e PASSWORD=mu -p 8787:8787 stnava/antsxdockergpu:latest
```

