FROM nginx

LABEL NAME="antaema/docker_images"
LABEL VERSION="nginx"

RUN apt-get update  &&  apt-get install -y curl gnupg gnupg2 gnupg1 nginx gettext  nodejs npm && \
    npm install --global yarn gulp && apt clean -y --dry-run
