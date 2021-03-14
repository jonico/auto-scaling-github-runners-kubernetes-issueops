FROM summerwind/actions-runner:latest

RUN sudo apt update -y \
  && sudo apt install gettext-base \
  && sudo apt install stress \
  && sudo apt install -y python3-pil \
  && sudo apt install -y python3-redis \
  && sudo apt install -y  python3-pip \
  && sudo pip3 install conan \
  && sudo apt-get install -y gcc-multilib \
  && curl -sLS https://dl.get-arkade.dev | sudo sh \
  && arkade get kubectl \
  && sudo mv /home/runner/.arkade/bin/kubectl /usr/local/bin/ \
  && arkade get kustomize \
  && sudo mv /home/runner/.arkade/bin/kustomize /usr/local/bin/ \
  && sudo apt-get install -y cmake \
  && sudo rm -rf /var/lib/apt/lists/*
