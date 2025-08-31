# Use Python 3.11 slim image as base
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PIP_NO_CACHE_DIR=1 \
    PIP_DISABLE_PIP_VERSION_CHECK=1

# Install system dependencies
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        gcc \
        g++ \
        && rm -rf /var/lib/apt/lists/*

# Copy requirements file (if you have one)
# COPY requirements.txt .

# Install Python dependencies
# RUN pip install -r requirements.txt

# Create a non-root user for security
RUN useradd --create-home --shell /bin/bash app \
    && chown -R app:app /app
USER app

# Expose port (modify as needed)
EXPOSE 8000

# Default command
CMD ["python", "-c", "print('Python environment is ready!')"]
