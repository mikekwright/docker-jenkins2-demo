FROM java:8

RUN apt-get update && \
    apt-get install -y curl git unzip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV JENKINS_URL http://mirrors.jenkins-ci.org/war/2.2/jenkins.war
RUN mkdir -p /var/jenkins && \
    mkdir -p /var/jenkins-install && \
    curl -sSL -o /var/jenkins-install/jenkins.war $JENKINS_URL

ENV JENKINS_HOME /var/jenkins
ENV JENKINS_SLAVE_AGENT_PORT 50000

ENV COPY_REFERENCE_FILE_LOG $JENKINS_HOME/copy_reference_file.log

VOLUME /var/jenkins

WORKDIR /var/jenkins

EXPOSE 8080 50000
ADD startup /startup

CMD ["/startup"]


