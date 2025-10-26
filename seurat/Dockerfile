# Use the existing satijalab/seurat image as the base image
FROM satijalab/seurat:latest

# Update R to the latest version
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    r-base curl rsync && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install DropletUtils
RUN R -e "if (!requireNamespace('BiocManager', quietly = TRUE)) install.packages('BiocManager'); BiocManager::install('DropletUtils')"

# Download the SeuratDisk source archive and install locally
RUN curl -L -o seurat-disk.zip https://github.com/mojaveazure/seurat-disk/archive/refs/heads/master.zip && \
    R -e "if (!requireNamespace('remotes', quietly = TRUE)) install.packages('remotes'); remotes::install_local('seurat-disk.zip')" && \
    rm seurat-disk.zip

# Add the R script with the MALAT1 threshold function.
# Execute permission is not needed because the script is not executed, just read by another script to get the function.
COPY malat1_function.R /usr/local/bin/
