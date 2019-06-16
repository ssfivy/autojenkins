# use jenkins blue ocean image
FROM jenkins/jenkins:lts-alpine

# We used JAVA_OPTS to disable the setup wizard.
# We won't need it since our setup will be fully automated.
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

# Next, we're copying the security.groovy file into /usr/share/jenkins/ref/init.groovy.d/ directory.
# Jenkins, when initialized, will execute all the Groovy scripts located in that directory.
# If you create additional setup scripts, that is the place you should place them.
COPY security.groovy /usr/share/jenkins/ref/init.groovy.d/security.groovy

# Finally, we are copying the plugins.txt file that contains the list of all the plugins we need
# and passing that list to the install-plugins.sh script which is part of the standard distribution.
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
