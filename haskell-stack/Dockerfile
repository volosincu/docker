FROM archlinux/base

RUN pacman -Syu --noconfirm
RUN pacman -S base-devel --noconfirm
RUN pacman -S stack emacs sudo less --noconfirm

#password = cabal - don't forget to change it
RUN useradd --system --create-home --shell /bin/bash -u 1000 haskell

RUN passwd -d haskell

USER haskell

RUN cd /home/haskell && stack ghci
