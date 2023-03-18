FROM nfcore/base:2.1
LABEL authors="Kaur ALasoo" \
      description="Glimpse 1.1.1 container"

# Install the conda environment
COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a

# Add conda installation dir to PATH (instead of doing 'conda activate')
ENV PATH /opt/conda/envs/nf-core-imputation-1.0dev/bin:$PATH

# Dump the details of the installed packages to a file for posterity
RUN conda env export --name nf-core-imputation-1.0dev > nf-core-imputation-1.0dev.yml

#Copy other binary dependencies
COPY bin/GLIMPSE_chunk /usr/bin/
COPY bin/GLIMPSE_concordance /usr/bin/
COPY bin/GLIMPSE_ligate /usr/bin/
COPY bin/GLIMPSE_phase /usr/bin/
COPY bin/GLIMPSE_sample /usr/bin/
COPY bin/GLIMPSE_snparray /usr/bin/
COPY bin/GLIMPSE_stats /usr/bin/
