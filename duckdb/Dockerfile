FROM continuumio/miniconda3

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Set work directory
WORKDIR /code

# Install dependencies
COPY requirement.txt /code/
RUN conda install -c conda-forge --file requirement.txt

# Copy project
COPY . /code/
