
FROM antaema/docker_images:arch

LABEL NAME="antaema/docker_images"
LABEL VERSION="latex"

RUN yay -Sy --noconfirm abntex2
# Install required packages
RUN yay --afterclean --removemake --save && sudo pacman -Sc && sudo pacman -Qtdq | xargs -r sudo pacman --noconfirm -Rcns && \
    sudo rm -rf /home/dev/.cache
