# Use an official Python runtime as the parent image
FROM python:3.10.13-slim-bullseye

# RUN apt update && \
# apt upgrade && \
# apt install -y build-essential
# Set the working directory in the container to /app
WORKDIR /app


# Allow statements and log 
COPY ./faa_chat_api.py /app/main.py
COPY ./my_deeplake /app/my_deeplake
# Copy the current directory contents into the container at /app
COPY ./requirements.txt /requirements.txt

# Install required packages
RUN pip install --no-cache-dir -r /requirements.txt

# Set environment variables
# Prevents Python from writing pyc files to disc (equivalent to python -B option)
ENV PYTHONDONTWRITEBYTECODE 1
# Prevents Python from buffering stdout and stderr (equivalent to python -u option)
ENV PYTHONUNBUFFERED 1
# Define environment variable for Flask's run command

ENV OPEN_API_KEY 1
# Expose the port the app runs on
EXPOSE 8000

# Define the command to run the app using Flask's development server
CMD ["python3", "main.py"]
