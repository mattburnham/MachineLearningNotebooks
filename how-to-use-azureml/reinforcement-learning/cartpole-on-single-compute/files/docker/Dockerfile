FROM mcr.microsoft.com/azureml/base:openmpi3.1.2-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    python-opengl \
    rsync \
    xvfb && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /usr/share/man/*

RUN conda install -y conda=4.7.12 python=3.6.2 && conda clean -ay && \
    pip install --no-cache-dir \
    azureml-defaults \
    azureml-dataprep[fuse,pandas] \
    azureml-contrib-reinforcementlearning \
    gputil \
    cloudpickle==1.3.0 \
    tensorboardX \
    tensorflow==1.14.0 \
    tabulate \
    dm_tree \
    lz4 \
    ray==0.8.3 \
    ray[rllib,dashboard,tune]==0.8.3 \
    psutil \
    setproctitle \
    gym[atari] && \
    conda install -y -c conda-forge x264='1!152.20180717' ffmpeg=4.0.2 && \
    conda install opencv