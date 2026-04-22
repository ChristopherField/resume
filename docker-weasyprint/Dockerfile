FROM python:3.11-slim

# Install system dependencies for WeasyPrint + Pandoc
RUN apt-get update && apt-get install -y \
    pandoc \
    libpango-1.0-0 \
    libpangoft2-1.0-0 \
    libcairo2 \
    libffi-dev \
    shared-mime-info \
    fonts-dejavu \
    fonts-liberation \
    && rm -rf /var/lib/apt/lists/*

# Install WeasyPrint
RUN pip install --no-cache-dir weasyprint

WORKDIR /data
