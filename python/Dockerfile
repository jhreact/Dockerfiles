# Base image
FROM taojonesin/ubuntu:trusty
MAINTAINER jhreact <jhreact@users.noreply.github.com>

# Install python
RUN \
  apt-get update && \
  apt-get install -y -q python python-dev python-pip python-virtualenv python-imaging python-docutils python-lxml mercurial && \
  rm -rf /var/lib/apt/lists/*

# Define working directory
WORKDIR /data

# Define default command
CMD ["bash"]
