# Use the official Miniconda image as the base image
FROM continuumio/miniconda3:25.3.1-1

# Update conda and create a new environment
RUN conda update -n base -c defaults conda -y \
    && conda create -n myenv python=3.10 pandas conda-forge::anndata conda-forge::scanpy conda-forge::python-igraph conda-forge::leidenalg conda-forge::numpy conda-forge::matplotlib conda-forge::memory_profiler -y \
    && conda clean -a -y

# Set up shell to activate the Conda environment automatically for all scripts and commands
SHELL ["conda", "run", "-n", "myenv", "/bin/bash", "-c"]

# Set the default Conda environment for all container executions
ENV CONDA_DEFAULT_ENV=myenv
ENV PATH=/opt/conda/envs/myenv/bin:$PATH

# Set the entrypoint to ensure all scripts run in 'myenv' environment by default
ENTRYPOINT ["/opt/conda/envs/myenv/bin/python"]
