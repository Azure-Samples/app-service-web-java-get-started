---
services: app-service\web
platforms: java
author: cephalin
---

# Java sample for Azure App Service - Coffee Shop

This is a Java coffee shop web app that you can deploy to Azure App Service. It uses the same WAR file as the Java 
Coffee Shop sample in the Azure Marketplace and demonstrates how Java apps are deployed to App Service.

To learn how to deploy this sample web app to App Service in a few minutes, go to 
[Get started with web apps in Azure App Service](https://azure.microsoft.com/en-us/documentation/articles/app-service-web-get-started/). 

> The purpose of this sample is *not* to demonstrate best-practice deployment of a Java web app, but to show you the exact
folder structure in App Service you should have when deploying a Java web app (see [Folder structure](#structure)). 
Keeping WAR files in a Git repository is not ideal. It is better to use 
[FTP](https://azure.microsoft.com/en-us/documentation/articles/web-sites-deploy/#howtoftp) or 
[content synchronization with a cloud folder])(https://azure.microsoft.com/en-us/documentation/articles/app-service-deploy-content-sync/).

### Serving Java apps in App Service

This sample uses the Tomcat server provided by App Service. You can serve Java web apps in 
[a variety of ways](https://azure.microsoft.com/en-us/documentation/articles/web-sites-java-custom-upload/): 
with a web server provided by App Service, with a custom server, or with a server embedded in your 
WAR/JAR.

<a name="structure">
### Folder structure

The main thing in the repo is a `webapps` folder with ROOT.war. The Tomcat/Jetty server in App Service
will look inside this folder for web apps to host. ROOT.war represents the default web app (at the site root). Any
WAR file that's otherwise named represents a web app accessbile at `~/<WARfilename>`. 

Also included in the repo is the Web.config file, that uses the 
[httpPlatformHandler](http://www.iis.net/downloads/microsoft/httpplatformhandler) to tell IIS to be a proxy between
HTTP requests and the Tomcat 8 server. You don't actually need this file if you enable Java for your app through the 
[portal](https://portal.azure.com) UI.

### License

See [LICENSE](LICENSE).
