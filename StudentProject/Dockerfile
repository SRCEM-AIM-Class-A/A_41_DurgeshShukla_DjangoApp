FROM python:3.9-slim

# Set working directory
WORKDIR /app

# First copy only requirements to leverage Docker cache
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy all files
COPY . .

# Run Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]