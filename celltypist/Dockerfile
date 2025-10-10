# Use the official Miniconda image as the base image
FROM continuumio/miniconda3

RUN conda update -n base -c defaults conda -y \
    && conda create -n myenv python=3.9 conda-forge::scanpy conda-forge::matplotlib bioconda::celltypist conda-forge::numba=0.53.0 -y \
    && conda clean -a -y

# Set up shell to activate the Conda environment automatically for all scripts and commands
SHELL ["conda", "run", "-n", "myenv", "/bin/bash", "-c"]

# Set the default Conda environment for all container executions and the celltypist models location
ENV CONDA_DEFAULT_ENV=myenv
ENV PATH=/opt/conda/envs/myenv/bin:$PATH
ENV CELLTYPIST_FOLDER=/celltypist_models

# Download celltypist models
RUN python -c "import celltypist; from celltypist import models; models.download_models(force_update=True)"

# Set the entrypoint to ensure all scripts run in 'myenv' environment by default
ENTRYPOINT ["/opt/conda/envs/myenv/bin/python"]
