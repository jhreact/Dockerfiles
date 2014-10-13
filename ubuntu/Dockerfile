# Base image
FROM taojonesin/ubuntu-base:trusty
MAINTAINER jhreact <jhreact@users.noreply.github.com>

RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y -q build-essential && \
  apt-get install -y -q software-properties-common && \
  apt-get install -y -q curl git htop man unzip vim wget tmux && \
  rm -rf /var/lib/apt/lists/*


# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]
