---
title: "Enable New Product"
date: 2020-05-14T11:25:07+08:00
draft: false
---

One feature of Singleton is to provide translation for product, but before you can get real translation from Singleton, your translation bundle should be already existing in Singleton Service.

This page will show you details about adding your product defination and respective translation bundle to Singleton Service.

How to add new product(s) and respective translation bundle to Singleton Service?
-----------------------

Singleton provides 2 ways to do this:

### Using Singleton API
1. Go to Singleton Service swagger-ui: 
```
https://localhost:8090/i18n/api/doc/swagger-ui.html
or 
http://localhost:8091/i18n/api/doc/swagger-ui.html
```

2. Switch to v2 in **Select a spec** on upper right corner; 

3. Go to and expand *translation-sync-api*, you will find an API as below:

`PUT /i18n/api/v2/translation/products/{productName}/versions/{version} Update translation`

4. Then click **Try it out**;

5. Input your `productName/version/component/locale` and the translation messages;

6. Verify everthing is fine, click **Execute**, then the translation message will be pushed into Singleton Service, please use other **GET** API(s) to fetch the translation.

Notes:
- **productName/version** should be match with the value in **translationData**;

- You can ignore the input for parameters: *operationid/dataOrigin/machineTranslation/pseudo/requester*, these parameters are used for vmware internal translation server;

- For **locale** defination, please refer to CLDR [availableLocales](https://github.com/unicode-cldr/cldr-core/blob/master/availableLocales.json) and [defaultContent](https://github.com/unicode-cldr/cldr-core/blob/master/defaultContent.json)

### Copy translation bundle to the location that Singleton Service reads
1. Check the translation localtion in `singleton-0.1.0.jar\BOOT-INF\classes\application-bundle.properties`
```
#translation config
#the follow item the Directory can't end of file separator
translation.bundle.file.basepath =.
translation.synch.git.flag = true
```
By default, it's same location with the Singleton service jar file, to look at `translation.bundle.file.basepath`.

2. Create your translation bundle file following the structure, and name your file "messages_xx.json" (for example: messages_en.json):
```
{
	"component": "componentName",
	"locale": "en",
	"messages": {
		"key1": "value1",
		"key2": "value2"
	}
}
```

3. Copy your translation bunele files to `.\l10n\bundles\{productName}\{version}\{componentName}`, then restart Singleton Service to fetch the translation, as to refresh cache.