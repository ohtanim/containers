FROM sonarqube:latest  

# Switch to root user to be able to install packages.  
USER root  

# Install packages.  
RUN apt-get update  
RUN apt-get install -y vim wget zip gcc gfortran make libssl-dev pkg-config python3.12 python3-venv python3-pip pip 

# Install sonarqube scanner.  
WORKDIR /usr/src  

RUN wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-7.1.0.4889-linux-aarch64.zip

RUN unzip sonar-scanner-cli-7.1.0.4889-linux-aarch64.zip
RUN rm sonar-scanner-cli-7.1.0.4889-linux-aarch64.zip
RUN mv sonar-scanner-7.1.0.4889-linux-aarch64 /usr/lib/sonar-scanner  

# Create symbolic link.  
RUN ln -s /usr/lib/sonar-scanner/bin/sonar-scanner /usr/local/bin/sonar-scanner  
ENV SONAR_RUNNER_HOME=/usr/lib/sonar-scanner  

RUN mkdir /home/sonarqube
ENV HOME=/home/sonarqube
ENV SONAR_USER_HOME=/home/sonarqube
RUN chown -R sonarqube /home/sonarqube
RUN chmod 777 /home/sonarqube

# Switch back to the sonarqube environment.  
WORKDIR $SONARQUBE_HOME  
USER sonarqube  
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
