---
title: "Installation"
date: 2019-09-24T20:04:26+08:00
draft: false
Weight: 10
---

After downloading Singleton Build from [Download](https://vmware.github.io/singleton/docs/get-started/download/) page, now you can setup Singleton to your environment.

# Prerequisites
* [JDK8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) is installed and works well on your environment, as Singleton Service is based on JAVA language development.
* The ports (8088, 8090, 8091) are allowed to access and not in use, as Singleton service run based on these ports.

# Installation
### Singleton Service
Singleton Service include 2 types of build, one is i18n manager, one is l10n manager. 
- I18n manager is the main build, it provides the [restful APIs](https://vmware.github.io/singleton/docs/overview/singleton-service/singleton-service-apis/) to talk with Singleton SDK.
- L10n manager will work together with I18n manager to achieve the feature [Source Collection](https://vmware.github.io/singleton/docs/overview/singleton-service/configurations/enable-source-collection/).

**To start Singleton Service I18n manager**
```
java -jar singleton-manager-i18n-x.x.x.jar
```
**To Start Singleton Service L10n manager**
```
java -jar singleton-manager-l10n-x.x.x..jar
```

### Singleton SDK
* [How to integrate with Singleton Java client](https://vmware.github.io/singleton/docs/tutorials/integrate-singleton-in-java-app/)
* [How to integrate with Singleton Javascript client](https://vmware.github.io/singleton/docs/tutorials/integrate-singleton-in-javascript-app/)
* [How to integrate with Singleton Angular client](https://vmware.github.io/singleton/docs/tutorials/integrate-singleton-in-angular-app/)
