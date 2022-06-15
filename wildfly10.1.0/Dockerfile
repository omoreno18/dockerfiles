# Base image
FROM jboss/wildfly:10.1.0.Final

 
# Maintainer
LABEL MAINTAINER="osk"
 
# Create user osk with password osk1234
RUN /opt/jboss/wildfly/bin/add-user.sh osk osk1234 --silent
 
# Add custom configuration file
ADD standalone.xml /opt/jboss/wildfly/standalone/configuration/
 
# Add example.war to deployments
ADD example.war /opt/jboss/wildfly/standalone/deployments/
 
# JBoss ports
EXPOSE 8080 9990 8009
 
# Run
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0", "-c", "standalone.xml"]