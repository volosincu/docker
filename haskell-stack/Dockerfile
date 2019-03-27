FROM archlinux/base

RUN pacman -Syu --noconfirm
RUN pacman -S base-devel --noconfirm
RUN pacman -S stack emacs --noconfirm
RUN pacman -Syy --noconfirm
RUN stack ghci
