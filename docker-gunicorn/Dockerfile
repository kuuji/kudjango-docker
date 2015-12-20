FROM ubuntu:14.04

# Set the file maintainer (your name - the file's author)
MAINTAINER Michal Karzynski

# Update the default application repository sources list
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y python python-pip python-mysqldb

RUN mkdir /srv/logs

# Copy application source code to SRCDIR
RUN mkdir /app
COPY python /app/

#Update pip
RUN pip install -U pip
# Install Python dependencies
RUN pip install -r /app/requirements.txt


# Port to expose
EXPOSE 8000

# Copy entrypoint script into the image
WORKDIR /app
COPY ./run.sh /
ENTRYPOINT ["/run.sh"]
