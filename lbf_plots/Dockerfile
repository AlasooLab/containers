FROM bioconductor/bioconductor_docker:RELEASE_3_15
LABEL authors="Ida Rahu" \
      description="Docker image for creating lbf graphs"

RUN R -e "BiocManager::install(c('data.table', 'dplyr', 'ggplot2', 'tidyverse', 'GGally'))"