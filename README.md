This repository is created for learning container development with OpenGL support. fsl and fsleyes in particular, are the target software.

View FSL license below:  https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/Licence
A salient clause of the license states it is not free for commercial use. So, if you use this image, make sure you are aware of that limitation. 
The maintainer of this image is not and cannot be held liable for unlawful use of this image

Table of Contents
=================

   * [Environment](#environment)
      * [(i) Docker](#i-docker)
      * [(ii) Singularity](#ii-singularity)
   * [Docker fsl image](#docker-fsl-image)
   * [Singularity fsl image](#singularity-fsl-image)

Table of contents created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)


# Environment

A separate repository details requisite software and environment. See https://github.com/tashrifbillah/glxgears-containers
In particular, the following sections should be useful:

## (i) Docker

https://github.com/tashrifbillah/glxgears-containers#linuxmac

https://github.com/tashrifbillah/glxgears-containers#windows


## (ii) Singularity

https://github.com/tashrifbillah/glxgears-containers#linuxmac-1

https://github.com/tashrifbillah/glxgears-containers#windows-1



# Docker fsl image


(i) build

> docker build -t tbillah/fsl-6.0.1-centos7 -f Dockerfile.centos7 .


(ii) push

> docker push tbillah/fsl-6.0.1-centos7


(iii) pull

> docker pull tbillah/fsl-6.0.1-centos7


(iv) run

**Linux/OSX**

> docker run --rm -ti --privileged -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix tbillah/fsl-6.0.1-centos7

Details can be found [here](https://github.com/tashrifbillah/glxgears-containers#linuxmac)


**Windows**

Follow steps mentioned [here](https://github.com/tashrifbillah/glxgears-containers#windows) and use `tbillah/fsl-6.0.1-centos7` instead of `glxgears-docker`. Eventually, you would use

> docker run --rm -ti --privileged -e DISPLAY=$DISPLAY tbillah/fsl-6.0.1-centos7


# Singularity fsl image


(i) build

> singularity build fsl-6.0.1-centos7 Singularity.centos7


(ii) push

> singularity push fsl-6.0.1-centos7 library://tbillah/collection/fsl-6.0.1-centos7


(iii) pull

> singularity pull library://tbillah/collection/fsl-6.0.1-centos7


(iv) run

**Linux/OSX**

> singularity shell --writable-tmpfs fsl-6.0.1-centos7
    
    (inside the shell) fsleyes

Details can be found [here](https://github.com/tashrifbillah/glxgears-containers#linuxmac-1)


**Windows**

You need a GUI desktop to run Singularity containers. Follow steps mentioned [here](https://github.com/tashrifbillah/glxgears-containers#windows-1). Eventually, you would use

> singularity shell --writable-tmpfs fsl-6.0.1-centos7

    (inside the shell) fsleyes



