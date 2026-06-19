FROM python:3.10-slim

WORKDIR /app

# Install system dependencies needed for some ML libraries
RUN apt-get update && apt-get install -y gcc && rm -rf /var/lib/apt/lists/*

# Copy and install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the code (including your .pkl model files)
COPY . .

# Expose the FastAPI port
EXPOSE 8000

# Start the Uvicorn server
CMD ["uvicorn", "recommender_api:app", "--host", "0.0.0.0", "--port", "8000"]