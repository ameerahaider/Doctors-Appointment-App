# Use the official Python 3.9 image as the base image
FROM python:3.9

# Set the working directory in the container
WORKDIR /app

# Copy the requirements.txt file to the container
COPY requirements.txt .

# Install the Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code to the container
COPY . .

# Expose the port that the application will listen on
EXPOSE 9090

# Start the application
CMD [ "python", "app.py" ]
