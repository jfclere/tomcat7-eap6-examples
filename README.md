tomcat7-eap6-examples
=====================
Those are the tomcat7 (2013/12/01) examples quickly arranged to use on EAP 6.2.

go to:  
http://www.jboss.org/jbossas/downloads/  
download latest EAP 6.2  
unzip it.  
download the jbossweb.jar (I am using 7.4.0.Beta1)  
'''Shell
wget https://repository.jboss.org/nexus/content/groups/public/org/jboss/web/jbossweb/7.4.0.Beta1/jbossweb-7.4.0.Beta1.jar
'''
copy the jbossweb jar on to the existing one: (I am using jboss-eap-6.2.0.Beta)
+++
cp jbossweb-7.4.0.Beta1.jar ./modules/system/layers/base/org/jboss/as/web/main/jbossweb-7.2.2.Final-redhat-1.jar
+++
make sure you use java 7
+++
[jfclere@jfcpc jboss-eap-6.2]$ java -version
java version "1.7.0_25"
Java(TM) SE Runtime Environment (build 1.7.0_25-b15)
Java HotSpot(TM) Server VM (build 23.25-b01, mixed mode)
+++
start jboss-eap:
+++
[jfclere@jfcpc jboss-eap-6.2]$ bin/standalone.sh 
+++
check out the adapted tomcat examples for github (https://github.com/jfclere/tomcat7-eap6-examples)
and build it:
+++
mvn install
+++
Deploy the example.war
+++
[jfclere@jfcpc jboss-eap-6.2]$ bin/jboss-cli.sh 
You are disconnected at the moment. Type 'connect' to connect to the server or 'help' for the list of supported commands.
[disconnected /] connect
[standalone@localhost:9999 /] deploy /home/jfclere/TMP/tomcat7-eap6-examples/examples.war
[standalone@localhost:9999 /] 
+++
Use a browser and go to http://localhost:8080/examples/websocket/index.xhtml
