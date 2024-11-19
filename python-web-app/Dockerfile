FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy the requirements and application files
COPY requirements.txt /app
COPY devops /app

# Install Python, pip, and virtualenv
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment
RUN python3 -m venv /app/venv

# Activate the virtual environment and install dependencies
RUN /app/venv/bin/pip install -r requirements.txt

# Expose the port for the Django app
EXPOSE 8000

# Use the virtual environment's Python for running the app
ENTRYPOINT ["/app/venv/bin/python"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]

