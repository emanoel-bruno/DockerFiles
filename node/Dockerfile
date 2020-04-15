
FROM antaema/docker_images:arch

LABEL NAME="antaema/docker_images"
LABEL VERSION="node"

RUN pacman -Sy --noconfirm nodejs yarn npm && \
    pacman -Sc && pacman -Qtdq | xargs -r pacman --noconfirm -Rcns && \
    pacman -Scc --noconfirm && rm -rf /home/dev/.cache
