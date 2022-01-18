### Tomcat
Tomcat is a server for hosting Java web applications.

## Three‐way handshake

## Antra class notes
### Web Resource
static rescources: Html, css, js, txt, mp4, jpg

Dynamic rescources: jsp pages, Servlet program

### Web Server
Tomcat: open source, lightweight javaWeb container

Jboss: open source, following JavaEE rules, pure Java EJ8 Server

GlossFish: robust commerical server

Resin: excellent performance, developed in Java

Weblogic: following JavaEE rules, adaptive for large-scale project

### Tomcat architecture
bin: executable files for Tomcat server

conf: config files for Tomcat server

lib: jar package for Tomcat server

logs: log info during Tomcat server runtime

temp: temp data during tomcat server runtime

webapps: deployed project

work: Servlet source code(jsp translation)/ session save and restore(SESSION.ser)

### Tomcat setup
download -- sh /Users/zoupeiyu/Documents/learn/Project/JavaEE/apache-tomcat-10.1.0-M8/bin/startup.sh -- browser "http://localhost:8080" - sh /Users/zoupeiyu/Documents/learn/Project/JavaEE/apache-tomcat-10.1.0-M8/bin/shutdown.sh  

MySQL default port: 3306

TomCat default port:8080

Change default port: must restart tomcat

HTTP default port: 80

coommon mistakes when starting tomcat( P106) : https://www.bilibili.com/video/BV1Y7411K7zz?p=105&spm_id_from=pageDriverhttps://www.bilibili.com/video/BV1Y7411K7zz?p=105&spm_id_from=pageDriver

Two method to deploy Tomcat

file proctocol

<img width="918" alt="image" src="https://user-images.githubusercontent.com/35554521/149866536-dd620145-a135-441d-a2f0-daeaa8326fad.png">

Web layer is Servlet

DAO is short for Data Access Object 

### package loss && disorder



# Servlet

