FROM ubuntu:14.04

# Install.
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common && \
  apt-get install -y byobu curl git htop man unzip vim wget && \
  rm -rf /var/lib/apt/lists/* && \
  curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash - && \
  sudo apt-get install -y nodejs  && \
  npm install -g pm2


# Add files.
ADD root/.bashrc /root/.bashrc
ADD root/.gitconfig /root/.gitconfig
ADD root/.scripts /root/.scripts

# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

VOLUME ["/data/code/app/logs"]

EXPOSE 30000
# Define default command.
CMD ["npm","start"]