FROM bioconductor/bioconductor_docker:RELEASE_3_15
LABEL authors="Kaur Alasoo" \
      description="Docker image to make regenie Manhattan plots"

RUN R -e "BiocManager::install(c('dplyr', 'optparse', 'readr', 'ggplot2','ggrepel'))"
