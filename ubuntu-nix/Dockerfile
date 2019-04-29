FROM ubuntu:18.04

RUN apt-get update \
 && apt-get install -y curl emacs vim less sudo git \
 && mkdir -p /nix /etc/nix \
 && chmod a+rwx /nix \
 && echo 'sandbox = false' > /etc/nix/nix.conf \
 && echo 'binary-caches = https://cache.nixos.org https://hydra.iohk.io' >> /etc/nix/nix.conf \
 && echo 'binary-cache-public-keys = hydra.iohk.io:f/Ea+s+dFdN+3Y/G+FDgSq+a5NEWhJGzdjvKNGv0/EQ=' >> /etc/nix/nix.conf


RUN useradd --system --create-home --shell /bin/bash -g root -G sudo -u 1000 user
#RUN adduser user --home /home/user --gecos "" --shell /bin/bash
RUN echo 'user:user' | chpasswd

CMD /bin/bash -l
USER user
ENV USER user
WORKDIR /home/user

RUN touch .bash_profile \
 && curl https://nixos.org/releases/nix/nix-2.2.2/install | sh

RUN . /home/user/.nix-profile/etc/profile.d/nix.sh

