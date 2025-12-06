# Is based on the latest ubuntu
FROM ubuntu:latest

# Update APT using apt-get update
RUN apt-get update

# Upgrade currently installed software through APT using apt-get upgrade -y
RUN apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove externally managed error (if needed)
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the Flask app into the container at /app
COPY ./api.py /app/api.py

# Make port 5252 available to the world outside this container
EXPOSE 5252

# Run the Flask app when the container starts
CMD ["python3", "api.py"]
