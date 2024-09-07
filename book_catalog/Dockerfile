# Dockerfile for book-catalog service

# Use a slim Python image as the base
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements.txt file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire book-catalog app into the container
COPY . /app

# Expose the port the app runs on
EXPOSE 8000

# Set environment variable for the database URL
ENV DATABASE_URL=${DATABASE_URL}

# Run the app using uvicorn (FastAPI or Starlette is assumed)
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
