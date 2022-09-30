FROM bioconductor/bioconductor_docker:RELEASE_3_15
LABEL authors="Ida Rahu" \
      description="Docker image for running R in finemapping pipeline"

RUN R -e "BiocManager::install(c('data.table', 'dplyr', 'optparse', 'readr', 'stringr', 'susieR', 'argparse', 'rfast', 'R.utils'))"