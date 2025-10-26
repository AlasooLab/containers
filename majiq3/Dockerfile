FROM continuumio/miniconda3
LABEL authors="Kaur Alasoo" \
      description="majiq3 container"

RUN apt-get -y update
RUN apt-get -y install libhts-dev python3-dev python3-pip git gcc libzstd-dev libbz2-dev

# Install the conda environment
COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a

# update yum
RUN apt-get -y update
RUN apt-get -y install libhts-dev python3-dev python3-pip git gcc

# Add conda installation dir to PATH (instead of doing 'conda activate')
ENV PATH /opt/conda/envs/nf-core-imputation-1.0dev/bin:$PATH

# Dump the details of the installed packages to a file for posterity
RUN conda env export --name nf-core-imputation-1.0dev > nf-core-imputation-1.0dev.yml

#Copy other binary dependencies
RUN pip install git+https://bitbucket.org/biociphers/majiq_academic.git@v3.0.11


