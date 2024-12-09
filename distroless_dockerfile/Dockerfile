# Step 1: Build stage
FROM python:3.9-slim AS builder

WORKDIR /app

# Copy the application code
COPY app.py .

# Install dependencies if any (None for this example)
RUN pip install --no-cache-dir --upgrade pip

# Step 2: Run stage with distroless image
FROM gcr.io/distroless/python3

# Copy the built application from the builder stage
COPY --from=builder /app /app

# Set the working directory
WORKDIR /app

# Run the application
CMD ["app.py"]
