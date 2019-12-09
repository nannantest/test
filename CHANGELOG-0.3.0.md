v0.3.0
-------

[Documentation](https://vmware.github.io/singleton/)

## Downloads for v0.3.0

### Service Binaries

filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-manager-i18n-s3-0.3.0.jar](http://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n-s3/0.3.0/singleton-manager-i18n-s3-0.3.0.jar) | - | master/[v0.3.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/)
[singleton-manager-i18n-0.3.0.jar](http://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-i18n/0.3.0/singleton-manager-i18n-0.3.0.jar) | - | master/[v0.3.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/)
[singleton-manager-l10n-0.3.0.jar](http://repo1.maven.org/maven2/com/vmware/singleton/singleton-manager-l10n/0.3.0/singleton-manager-l10n-0.3.0.jar) | - | master/[v0.3.0-Singleton-Service](https://github.com/vmware/singleton/releases/tag/)

### Client Binaries
filename | sha1 hash | branch/tag
-------- | --- | ------
[singleton-client-java.jar](#) | No update | g11n-javaclient/[v0.3.0-Singleton-Javaclient]
[@singleton-i18n/js-core-sdk](https://www.npmjs.com/package/@singleton-i18n/js-core-sdk) | - | No update
[@singleton-i18n/angular-client](https://www.npmjs.com/package/@singleton-i18n/angular-client) | - | No update

## Changelog since v0.2.0

### Main Changes
#### Service
- Add translation version fallback ([#82](https://github.com/vmware/singleton/issues/82))
- Support product white list ([#85](https://github.com/vmware/singleton/issues/85))
- Sort strings in translation bundles in alphabet order ([#123](https://github.com/vmware/singleton/issues/123))
- Support fetching translations of multiple components in one call ([#223](https://github.com/vmware/singleton/issues/223))
- Add relative time category (dateFields) in i18n formatting pattern API ([#224](https://github.com/vmware/singleton/issues/224))

#### SDK
#### Java Client
- Support customized header when sending request to Service ([#122](https://github.com/vmware/singleton/issues/122))
- Support fetching translations of multiple components in one call ([#219](https://github.com/vmware/singleton/issues/219))
- Support shared components ([#226](https://github.com/vmware/singleton/issues/226))


### Known Issues
#### Service
- Wrong localeID display when combination is valid while the pattern result is from different locale ([#311](https://github.com/vmware/singleton/issues/311))
- The product-white-list configuration files don't be loaded from S3 storage ([#316](https://github.com/vmware/singleton/issues/316))
- Failed to get translation for all translation related APIs in Singleton S3 build ([#317](https://github.com/vmware/singleton/issues/317))
- Don't support version fallback in combination API ([#321](https://github.com/vmware/singleton/issues/321))


### Improvement
N/A


### Action Required
N/A
