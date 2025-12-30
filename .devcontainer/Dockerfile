FROM python:3.11-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Create jovyan user
RUN useradd -m -s /bin/bash jovyan

# Install Python packages
RUN pip install --no-cache-dir \
    jupyter \
    jupyterlab \
    pandas \
    geopandas \
    xarray \
    rasterio \
    matplotlib \
    numpy \
    dask \
    planetary-computer \
    pystac-client

# Create expected conda paths for compatibility
RUN mkdir -p /srv/conda/envs/notebook/bin && \
    ln -s /usr/local/bin/python /srv/conda/envs/notebook/bin/python

USER jovyan
WORKDIR /home/jovyan
