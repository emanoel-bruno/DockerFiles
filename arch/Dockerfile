
FROM archlinux

LABEL NAME="antaema/docker_images"
LABEL VERSION="arch"

RUN useradd -m -r -s /bin/bash dev && passwd -d dev && \
    mkdir -p /home/dev/.gnupg && \
    mkdir /build

RUN echo '[multilib]' >> /etc/pacman.conf && \
    echo 'Include = /etc/pacman.d/mirrorlist' >> /etc/pacman.conf && \
    echo 'dev ALL=(ALL) ALL' > /etc/sudoers && \
    echo 'standard-resolver' > /home/dev/.gnupg/dirmngr.conf

RUN pacman --noconfirm -Syyu base-devel git

RUN chown -R dev:dev /home/dev /build
RUN su - dev -c 'cd /build  && git clone --depth 1 https://aur.archlinux.org/yay.git && cd yay && makepkg --noconfirm -si'

RUN su - dev -c 'yay --afterclean --removemake --save' && pacman -Sc && pacman -Qtdq | xargs -r pacman --noconfirm -Rcns && \
    rm -rf /home/dev/.cache && rm -rf /build

WORKDIR /home/dev
USER dev
CMD ["sleep", "infinity"]
