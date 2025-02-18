
<!-- [![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/3673) -->

# Torch jupyter on hpc

Deep learning jupyter on hpc. You can run the deep learning environment by jupyterHpc.

<p align="center">
  <img src="src/logoCollection.png" alt="torchJupyterHpc" width="600" >
</p>


## How to start the env

This is based on singularity container. Make you have already loaded the singularity module or install the singularity module, then run the following codes to enable the container:

```
singularity shell --writable torchJupyterOnHpc.sif # the sif is removed since it is too large
```

Or your self-built sif files:

```
singularity shell --writable yourSif.sif
```

If you would like to build the sif by yourself, please refer to the following codes:


```
sh build.sh
```

## How to run the jupterHpc

Once you are in the env, it is the same way to start the jupyterHpc and enjoy your self. For jupyter lab/notebook on hpc, please refer to [jupyterHpc](https://github.com/jligm-hash/jupyterHpc). Here is an example:

```
sh runJupyterHpc.sh
```

## Other ways to run jupyter for you

[Install container](https://singularity-tutorial.github.io/01-installation/)

[Resources from EPFL](https://tube.switch.ch/videos/B6ZJYhSSrd)


## Previous README

This repository is folked on ylugithub/pytorch_gpu_singularity. README on ylugithub/pytorch_gpu_singularity is following:

<pre>

## Aim

- Quickly set up medial imaging deep learning research environment on Linux(singularity container based)
- GPU acceleration (CUDA and cuDNN included)
- Supported frameworks and packages:

    - PyTorch
    - Scikit-learn
    - OpenCV
    - SimpleITK
    - Scikit-image
    - Anaconda packages: https://docs.anaconda.com/anaconda/packages/py3.6_linux-64/


## Pre-requisite

- your host system must has an NVIDIA GPU card and a driver installed(you don't need to install cuda and cudnn)

- install singularity on your host

    ```bash
    # ubuntu
    sudo apt-get install -y singularity-container
    ```

- pull singularity image from singularity hub

    ```bash
    singularity pull --name pytorch_gpu.simg shub://yinglilu/pytorch_gpu_singularity:1.3.0
    ```

## Usage

### 1. enter into singularity container, run command in the container

```bash
# enter into singularityh container: imagine it as SSH into (passwordless) another machine
# --nv: leverage the nvidia gpu card
singularity shell --nv /containers/pytorch_gpu.simg
```

You will get:

```bash
Singularity: Invoking an interactive shell within container...

Singularity pytorch_gpu.simg:~>
```

You can type command now, for instance:

```bash
python /path/to/<your_script.py>
```

After finishing your work, type

```bash
exit
```

to exit the container.

#### note: /path/to/

- Singularity will bind your host's $HOME to container's $HOME automatically. That's mean, if you do modification on your host's home directory, you can see the modifications in the container's home directory, and vice versa.

- If current working directory is in your home directory or bind path, Singularity will replicate your current working directory within the container.

    Therefore, `/path/to/` can be a relative path or absolute path of your home or bind path.

## 2. run singularity container command directly

```bash
singularity exec --nv pytorch_gpu.simg python /path/to/<your_script.py>
```

</pre>
