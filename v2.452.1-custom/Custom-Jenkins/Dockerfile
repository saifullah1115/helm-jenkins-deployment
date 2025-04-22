FROM jenkins/jenkins:2.452.1-jdk17
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt

RUN jenkins-plugin-cli  --plugin-file /usr/share/jenkins/ref/plugins.txt

USER jenkins
