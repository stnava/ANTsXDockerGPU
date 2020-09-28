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

Some pointers on "getting it working"

From: https://github.com/tensorflow/tensorflow/issues/26182

```
export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

and please make sure you have a clean / recent install of docker and its relevant nvidia extensions https://docs.docker.com/config/containers/resource_constraints/
