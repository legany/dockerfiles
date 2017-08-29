# DESCRIPTION:    Create the Latex in a container
# AUTHOR:         Eugenio Cunha <eugenio@legany.com>
# COMMENTS:
#   This file describes how to build latex
#   in a container with all dependencies installed.
#   Tested on Debian Stretch.
# USAGE:
#   # Download atom Dockerfile
#   wget https://raw.githubusercontent.com/jessfraz/dockerfiles/master/atom/Dockerfile
#
#   # Build latex image
#   docker build -t latex .
#
#   # Create new container
#   sudo docker run -itd --name latex -v [host directory]:/Latex latex
#
#

# Base docker image
FROM debian:stretch

# Maintainer
MAINTAINER Eugenio Cunha <eugenio@legany.com>

# Label
LABEL version="1.1"

# Install wget, git, make and latex
RUN apt-get update && apt-get install -y \
  wget \
  git \
  make \
  texlive-full && \
  apt-get --purge remove -y .\*-doc$ && \
  apt-get clean -y

# Create directory Latex
RUN mkdir -p /Latex

# Worckdir
WORKDIR /Latex
