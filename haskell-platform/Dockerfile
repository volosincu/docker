FROM ubuntu:19.04

RUN apt-get update
RUN apt-get install -y software-properties-common
RUN apt-get update
RUN apt-get install -y emacs haskell-platform --fix-missing
RUN apt-get install -y less sudo

RUN useradd --system --create-home --shell /bin/bash -g root -G sudo -u 1000 haskell

RUN echo 'haskell:cabal' | chpasswd