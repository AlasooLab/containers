FROM nfcore/base:2.1
LABEL authors="Ida Rahu" \
      description="Docker image for calculating the LD matrix"

ENV LDSTORE_VERSION v2.0
# ADD ./docker/finemap-suite/ldstore_${LDSTORE_VERSION}_x86_64 /usr/bin/ldstore
RUN wget --quiet http://www.christianbenner.com/ldstore_${LDSTORE_VERSION}_x86_64.tgz -P ~ && \
    tar xf ~/ldstore_${LDSTORE_VERSION}_x86_64.tgz -C ~ && \
    cp ~/ldstore_${LDSTORE_VERSION}_x86_64/ldstore_${LDSTORE_VERSION}_x86_64 /usr/bin/ldstore && \
    rm -r ~/ldstore_${LDSTORE_VERSION}_x86_64*

# Install the conda environment
COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
# Add conda installation dir to PATH (instead of doing 'conda activate')
ENV PATH /opt/conda/envs/finemap/bin:$PATH
# Dump the details of the installed packages to a file for posterity
RUN conda env export --name finemap > finemap.yml

RUN chmod 777 /usr/bin/ldstore
RUN apt-get clean && apt-get update && apt-get install -y libgomp1