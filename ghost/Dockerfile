############################################################
# Dockerfile file to build Node.js container images
# AUTHOR: Axel Quack <mail@axelquack.de>
# Version 0.1
############################################################

# Pull base image.
FROM guttertec/nodejs
MAINTAINER Axel Quack <mail@axelquack.de>

# Install Ghost
RUN \
  cd /tmp && \
  wget https://ghost.org/zip/ghost-latest.zip && \
  unzip ghost-*.zip -d /ghost && \
  rm -f ghost-*-latest.zip && \
  cd /ghost && \
  npm install --production && \
  sed 's/127.0.0.1/0.0.0.0/' /ghost/config.example.js > /ghost/config.js && \
  useradd ghost --home /ghost

# Add files.
ADD start.bash /ghost-start

# Set environment variables.
ENV NODE_ENV production

# Define mountable directories.
VOLUME ["/data", "/ghost-override"]

# Define working directory.
WORKDIR /ghost

# Define default command. Make sure you have zsh already installed.
CMD ["zsh", "/ghost-start"]

# Expose ports.
EXPOSE 2368