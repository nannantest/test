- [v0.5.0](#v050)
  - [Downloads for v0.5.0](#downloads-for-v050)
    - [Service Binaries](#service-binaries)
    - [Client Binaries](#client-binaries)
  - [Changelog since v0.4.0](#changelog-since-v040)
    - [Main Changes](#main-changes)
      - [Service](#service)
      - [SDK](#sdk)
    - [Known Iusses](#known-issues)
    - [Improvement](#improvement)
    - [Action Required](#action-required)

v0.5.0
-------
[Documentation](https://vmware.github.io/singleton/)

## Downloads for v0.5.0

### Service Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-manager-i18n-s3-0.5.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n-s3/0.5.0/singleton-manager-i18n-s3-0.5.0.jar) | `` | master/[v0.5.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-Service)
[singleton-manager-i18n-0.5.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n/0.5.0/singleton-manager-i18n-0.5.0.jar) | `` | master/[v0.5.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-Service)
[singleton-manager-l10n-0.5.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-l10n/0.5.0/singleton-manager-l10n-0.5.0.jar) | `` | master/[v0.5.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-Service)

### Client Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-client-java-0.5.0.jar](https://repo1.maven.org/maven2/com/vmware/singleton/singleton-client-java/0.5.0/singleton-client-java-0.5.0.jar) | `c8db72dd399af38be5682bd4fa4f59325b486170` | g11n-java-client/[v0.5.0-Singleton-Javaclient](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-Java-Client)
[@singleton-i18n/js-client](https://www.npmjs.com/package/@singleton-i18n/js-core-sdk/v/0.5.0--) | `` | g11n-js-client/[v0.5.0-Singleton-JS-Client](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-JS-Client)
[@singleton-i18n/nodejs-client](https://www.npmjs.com/package/@singleton-i18n/js-core-sdk-server/v/0.5.0--) | `` | g11n-js-client/[v0.5.0-Singleton-JS-Client](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-JS-Client)
[@singleton-i18n/angular-client](https://www.npmjs.com/package/@singleton-i18n/angular-client/v/0.2.0) | - | No update
[singleton-go-client](https://github.com/vmware/singleton/tree/g11n-go-client) | - | g11n-go-client/[v0.5.0-Singleton-Go-Client](https://github.com/vmware/singleton/releases/tag/v0.5.0-Singleton-Go-Client)

## Changelog since v0.4.0

### Main Changes
#### Service
- Support more fomatting options for langauge displayName in getSupportedLanguageList API ([#361](https://github.com/vmware/singleton/issues/361))
- Add etag/max-age in Translation APIs response ([#442](https://github.com/vmware/singleton/issues/442))
- Support to customize more items for cache-control ([#482](https://github.com/vmware/singleton/issues/482))
- Add scopeFilter to pattern API ([#515](https://github.com/vmware/singleton/issues/515))
- Add pattern data about compact number formats ([#555](https://github.com/vmware/singleton/issues/555))
- Add Microsoft Translator API Regional Source Support ([#566](https://github.com/vmware/singleton/pull/566))
- Support to customize API request header buffer size ([#586](https://github.com/vmware/singleton/issues/586))
- Add pattern data numberingSystems for Numbers ([#616](https://github.com/vmware/singleton/issues/616)) 
- Add key-based GET API ([#648](https://github.com/vmware/singleton/issues/648))
- Add API to GET localized city name list ([#675](https://github.com/vmware/singleton/issues/675)), currently only English city name returned
- Compress Singleton Service responses to improve UI performance ([#747](https://github.com/vmware/singleton/issues/747))
- Fixed - Don't support version fallback in getSupportedLanguageList API ([#338](https://github.com/vmware/singleton/issues/338))
- Fixed - Add copyright and license info in more code files ([#366](https://github.com/vmware/singleton/issues/366), [#397](https://github.com/vmware/singleton/issues/397))
- Fixed - Failed to get pattern data when request non-existing product in combination API ([#372](https://github.com/vmware/singleton/issues/372))
- Fixed - No parameter verification for some fileds in combination API ([#373](https://github.com/vmware/singleton/issues/373), [#495](https://github.com/vmware/singleton/issues/495))
- Fixed - Missing settings.gradle under tools\tool-cldr-extractor ([#651](https://github.com/vmware/singleton/issues/651))

#### SDK
#### JS Client

#### Go Client


### Known Issues
#### Service


#### Go Client

### Improvement
#### Service
- Upgrade tomcat to 9.0.37 ([#665](https://github.com/vmware/singleton/issues/665))
- Upgrade ant to 1.10.8 ([#613](https://github.com/vmware/singleton/issues/613))
- Upgrade log4j to 2.13.2 ([#563](https://github.com/vmware/singleton/issues/563))
- Upgrade guava to 20.0 ([#581](https://github.com/vmware/singleton/issues/581))
- Upgrade jackson-databind to 2.11.2, commons-collections to 3.2.2 ([#737](https://github.com/vmware/singleton/issues/737))

#### JS Client

### Action Required
- The **POST** combination API will be deprecated, please replace it by **GET** API
- Remove fallback to en content when the translation no exist for request locale ([#468](https://github.com/vmware/singleton/issues/468)), please pay attention if you use Singleton Service API directly, suggest to use Singleton Client to avoid this kind of issue