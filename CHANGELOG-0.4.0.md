v0.4.1
-------
[Documentation](https://vmware.github.io/singleton/)

## Downloads for v0.4.1

### Service Binaries

filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-manager-i18n-s3.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n-s3/) | - | No update
[singleton-manager-i18n.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n/) | - | No update
[singleton-manager-l10n.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-l10n/) | - | No update

### Client Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-client-java-0.4.1.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-client-java/0.4.1/singleton-client-java-0.4.1.jar) | No update | g11n-javaclient/[v0.4.1-Singleton-Javaclient](https://github.com/vmware/singleton/releases/tag/v0.4.1-Singleton-Java-Client)
[@singleton-i18n/js-core-sdk](https://www.npmjs.com/package/@singleton-i18n/js-core-sdk) | - | No update
[@singleton-i18n/angular-client](https://www.npmjs.com/package/@singleton-i18n/angular-client) | - | No update
[singleton-go-client](#) | - | No update

## Changelog since v0.4.0

### Main Changes
#### SDK
#### Java Client
- Improve log level defination ([#416](https://github.com/vmware/singleton/pull/416))

v0.4.0
-------
[Documentation](https://vmware.github.io/singleton/)

## Downloads for v0.4.0

### Service Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-manager-i18n-s3-0.4.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n-s3/0.4.0/singleton-manager-i18n-s3-0.4.0.jar) | `` | master/[v0.4.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-Service)
[singleton-manager-i18n-0.4.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n/0.4.0/singleton-manager-i18n-0.4.0.jar) | `` | master/[v0.4.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-Service)
[singleton-manager-l10n-0.4.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-l10n/0.4.0/singleton-manager-l10n-0.4.0.jar) | `` | master/[v0.4.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-Service)

### Client Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-client-java-0.4.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-client-java/0.4.0/singleton-client-java-0.4.0.jar) | No update | g11n-javaclient/[v0.4.0-Singleton-Javaclient](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-Java-Client)
[@singleton-i18n/js-core-sdk](https://www.npmjs.com/package/@singleton-i18n/js-core-sdk) | - | g11n-js-client/[v0.4.0-Singleton-JS-Client](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-JS-Client)
[@singleton-i18n/angular-client](https://www.npmjs.com/package/@singleton-i18n/angular-client) | - | No update
[singleton-go-client](#) | - | g11n-go-client/[v0.4.0-Singleton-Go-Client](https://github.com/vmware/singleton/releases/tag/v0.4.0-Singleton-Go-Client)

## Changelog since v0.3.0

### Main Changes
#### Service
- Add Singleton Service lite version to optimize performance ([#248](https://github.com/vmware/singleton/issues/248))
- Singleton Service lite version also support AWS S3 storage ([#325](https://github.com/vmware/singleton/issues/325))
- Add start-up/health-check script for Singleton Service, please refer to [Singleton Service Script](https://vmware.github.io/singleton/docs/overview/singleton-service/singleton-service-script/) ([#283](https://github.com/vmware/singleton/issues/283))
- Add a new **GET** combination API to fix issue ([#321](https://github.com/vmware/singleton/issues/321)) and issue ([#322](https://github.com/vmware/singleton/issues/322))
- Fixed - Wrong localeID display when combination is valid while the pattern result is from different locale ([#311](https://github.com/vmware/singleton/issues/311))
- Fixed - The product-white-list configuration files don't be loaded from S3 storage ([#316](https://github.com/vmware/singleton/issues/316))
- Fixed - Failed to get translation for all translation related APIs in Singleton S3 build ([#317](https://github.com/vmware/singleton/issues/317))
- Fixed - The pseudo tag is repeated depends on the calls counts with translation-product-api ([#336](https://github.com/vmware/singleton/issues/336))
- Fixed - NullPointerException occurs in scheduled task in Singleton Service lite version ([#346](https://github.com/vmware/singleton/issues/346))

#### SDK
#### JS Client
- Support fetching translations of multiple components in one call ([#220](https://github.com/vmware/singleton/issues/220))

#### Go Client
This is a new Singleton SDK, we support translation-related APIs in current version ([#343](https://github.com/vmware/singleton/issues/343)). 
For more details, please refer to [here](https://github.com/vmware/singleton/blob/g11n-go-client/README.md).

### Known Issues
#### Service
- Don't support version fallback in getSupportedLanguageList API ([#338](https://github.com/vmware/singleton/issues/338))
- Failed to get pattern data when request non-existing product in combination API ([#372](https://github.com/vmware/singleton/issues/372))
- No parameter verification for some fileds in combination API ([#373](https://github.com/vmware/singleton/issues/373))

#### Go Client
- No translation returned if one of requesting component is not existing even though the another is available ([#384](https://github.com/vmware/singleton/issues/384))

### Improvement
#### Service
- Upgrade tomcat to 9.0.30 ([#355](https://github.com/vmware/singleton/issues/355))
- Upgrade snakeyaml to 1.25 ([#339](https://github.com/vmware/singleton/issues/339))
- Upgrade spring boot to 2.2.4.RELEASE and  spring framework to 5.2.3.RELEASE ([#368](https://github.com/vmware/singleton/issues/368))

#### JS Client
- Optimize code format: change double quotes to single quotes ([#338](https://github.com/vmware/singleton/issues/338))

### Action Required
N/A
