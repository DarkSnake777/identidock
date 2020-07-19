FROM jenkins/jenkins:jdk11

USER root
RUN apt-get update && apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common  && apt-get install -y sudo  && curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add &&   add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable" &&  apt-get update && apt-get install -y docker-ce docker-ce-cli containerd.io && rm -rf /var/lib/apt/lists/*
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers
RUN curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" > /usr/local/bin/docker-compose; chmod +x usr/local/bin/docker-compose
USER jenkins 
RUN /usr/local/bin/install-plugins.sh git greenballs
