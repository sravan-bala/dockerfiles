############################################################
# Dockerfile file to build Hubot Scripts container images
# AUTHOR: Axel Quack <mail@axelquack.de>
# Version 0.1
############################################################

# Pull base image.
FROM guttertec/hubot
MAINTAINER Axel Quack <mail@axelquack.de>

# Add scripts
ADD scripts/advice.coffee /root/mybot/scripts/advice.coffee
ADD scripts/bitcoin.coffee /root/mybot/scripts/bitcoin.coffee
ADD hubot-scripts.json /root/mybot/hubot-scripts.json

# Install npm libraries
WORKDIR /root/mybot
RUN npm install cron cheerio