FROM nfcore/base:2.1
LABEL authors="Kaur Alasoo" \
      description="Docker image for regenie"

# Install the conda environment
COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a

# Add conda installation dir to PATH (instead of doing 'conda activate')
ENV PATH /opt/conda/envs/regenie/bin:$PATH

# Dump the details of the installed packages to a file for posterity
RUN conda env export --name regenie > regenie.yml
