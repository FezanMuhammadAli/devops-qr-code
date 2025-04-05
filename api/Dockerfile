# Use the official Python 3.9 image as the base image
FROM python:3.9

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the requirements file into the container
COPY requirements.txt ./

# Install the Python dependencies specified in requirements.txt
# The --no-cache-dir option prevents caching to reduce image size
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire application code into the container
COPY . .

# Specify the command to run the application using Uvicorn
# --host 0.0.0.0 makes the app accessible externally
# --port 80 specifies the port the app will run on
# --reload enables auto-reloading during development (not recommended for production)
CMD ["uvicorn", "main:app", "--host","0.0.0.0", "--port","80", "--reload"]