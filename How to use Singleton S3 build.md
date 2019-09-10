Overview
-------------------
By default, Singleton Service build will include the translation bundle files. Now we add a new feature to support to store the translation bundle files on AWS S3.


How to generate Singleton Service S3 build?
------------------
The steps to generate S3 build:
1. Clone Singleton Service code using Git.
```
git clone git@github.com:vmware/singleton.git
```
2. Update the complie configuration file `singleton/g11n-ws/gradle.properties`

```
datatype=bundle
``` 
to 
```
datatype=s3
```

3. Update the below s3 config items according to your requirements in `singleton/g11n-ws/vip-manager-i18n/src/main/resources/application-s3.properties`
```
#S3 store config
s3.accessKey=#####
s3.secretkey=######
s3.region=######
s3.bucketName=######
```

4. Complie a build using Gradle under singleton/g11n-ws
```
./gradlew build
```
Jar files will be generated to
```
singleton/publish (Eg. singleton/publish/vip-manager-i18n-0.1.0.jar)
```

Resouces files
-----------------
The translation bundle files structure in AWS S3:
```
[bucket name]/l10n/bundles/[product name]/[version]/[component name]/messages_xx.json
```
