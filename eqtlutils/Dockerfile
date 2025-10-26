FROM bioconductor/bioconductor_docker:RELEASE_3_13
LABEL authors="Kaur Alasoo" \
      description="Docker image containing all requirements for the eQTLUtils R package and pipeline"

RUN R -e "BiocManager::install(c('remotes','BiocCheck','SummarizedExperiment','lumi', 'limma', 'dplyr','cqn','ggplot2','htmlwidgets','tidyr','assertthat','devtools','GenomicRanges','readr', 'GDSArray','plotly','gridExtra','cli','R.utils'))"
RUN R -e "remotes::install_github('kauralasoo/eQTLUtils@v22.11.1')"
