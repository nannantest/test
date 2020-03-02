---
title: "Singleton Service build Script"
date: 2019-09-24T20:05:55+08:00
draft: false
---
Singleton adds script files to help user to start/check/stop Singleton Service build.

# How to Generate Singleton Script
The steps:

1. Clone Singleton Service code using Git
```
git clone git@github.com:vmware/singleton.git
```

2. Complie a build using Gradle wrapper under `./g11n-ws` folder
```
./gradlew build -x test
```

3. Go to `./Singleton/Publish` folder, find `singletonScripts-0.1.0.zip`, and extract it, you will get 4 files as below:
```
singletonall.sh
singletonstart.sh
singletoncheck.sh
singletonstop.sh
```