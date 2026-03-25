# --- Stage 1: Builder ---
FROM python:3.10-slim AS builder

WORKDIR /build

# Install build dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
   build-essential gcc gfortran && \
   rm -rf /var/lib/apt/lists/*

# Install packages into a local folder
COPY requirements.txt .
RUN pip install --no-cache-dir --prefix=/install -r requirements.txt


# --- Stage 2: Deployment ---
FROM python:3.10-slim

# Setup user 1000
RUN groupadd -g 1000 app && \
    useradd -u 1000 -r -g app -d /app -s /usr/sbin/nologin app

WORKDIR /app

# Copy only the installed site-packages from builder
COPY --from=builder /install /usr/local

# Copy application files and set ownership DURING the copy
COPY --chown=root:root . .

# Create output dir with correct permissions
RUN mkdir -p /app/output && \
    chown 1000:1000 /app/output && \
    chmod 0700 /app/output && \
    chmod 0555 /app # Make /app read-only for the app user

# Switch to non-root user 
USER 1000

CMD ["python", "main.py"]
