
FROM antaema/docker_images:arch

LABEL NAME="antaema/docker_images"
LABEL VERSION="latex"
USER dev

RUN yay -Sy --noconfirm abntex2 texlive-latexindent-meta && \
    yay --afterclean --removemake --save && \
    sudo pacman -Sc && sudo pacman -Qtdq | xargs -r sudo pacman --noconfirm -Rcns && \
    sudo rm -rf /home/dev/.cache
