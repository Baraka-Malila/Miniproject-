# Use an official Python runtime as the base image
FROM python:3.10-slim

# Set environment variables
ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8

# Install system dependencies (basic ones you may need)
RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install --upgrade pip
RUN pip install jupyterlab tensorflow numpy pandas matplotlib scikit-learn seaborn plotly optuna tqdm h5py

# Set the working directory
WORKDIR /workspace

# Expose Jupyter Lab port
EXPOSE 8888

# Start Jupyter Lab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser"]
