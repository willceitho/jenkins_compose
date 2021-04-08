FROM jenkins/jenkins:lts
ENV CASC_JENKINS_CONFIG=/usr/share/jenkins/ref/casc_configs/

COPY jenkins.yml /usr/share/jenkins/ref/casc_configs/jenkins.yml
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt

USER root
RUN chown -R  jenkins: /usr/share/jenkins/ref/

RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

RUN adduser jenkins users

# RUN apt-get -y update && \
#  apt-get -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common && \
#  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - 
 
# RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian/buster/stable"
# RUN apt-get update && \
#  apt-get -y install docker-ce docker-ce-cli containerd.io
# RUN curl -L “https://github.com/docker/compose/releases/download/1.28.4/docker-compose-$(uname -s)-$(uname -m)” -o /usr/local/bin/docker-compose && \
#  chmod +x /usr/local/bin/docker-compose && \
#  ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
# USER jenkins
