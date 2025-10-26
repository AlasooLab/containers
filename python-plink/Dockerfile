FROM quay.io/biocontainers/plink:1.9.0b.7.7--h7b50bb2_0

FROM python:3.10.16-bullseye

# Put plink into the python image
COPY --from=0 /usr/local/bin/plink /usr/local/bin/plink

# Install pandas and matplotlib
RUN pip install pandas matplotlib
