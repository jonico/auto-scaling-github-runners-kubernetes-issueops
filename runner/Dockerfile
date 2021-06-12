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
  && sudo pip3 install pymysql \
  && sudo wget https://github.com/planetscale/cli/releases/download/v0.46.0/pscale_0.46.0_linux_amd64.deb \
  && sudo dpkg -i pscale_0.46.0_linux_amd64.deb \
  && sudo rm -rf /var/lib/apt/lists/*
