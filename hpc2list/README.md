# singularity-docker-centos7-conda-tf2-pytorch
centos7 container with miniconda , tensorflow2 and pytorch with gpu support (cuda 10.1)

Building:
```
sudo singularity build hpc2-pytorch.sif Singularity # make sure the image buiding list has the same name with image name
```




# notes

hpc2WithR.sif
is suitable for the jupyter lab

centos6_.*.sif
could not use the jupyter lab

hpc2-admri.sif & 02.sif
the NVIDA driver is too old