FROM alpine:latest

# Install Python 3, pip, and virtual environment tools
RUN apk add --update python3 py3-pip && rm -rf /var/cache/apk/*

# Create a virtual environment and activate it
RUN python3 -m venv /usr/src/app/venv
RUN . /usr/src/app/venv/bin/activate

# Install dependencies within the virtual environment
COPY requirements.txt /usr/src/app/
RUN /usr/src/app/venv/bin/pip install --no-cache-dir -r /usr/src/app/requirements.txt

# Copy application files into the virtual environment
COPY . /usr/src/app/

# Expose the port for the Flask application
EXPOSE 5000

# Use the virtual environment to run the application
CMD ["/usr/src/app/venv/bin/python3", "/usr/src/app/app.py"]

