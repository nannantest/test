Singleton Service add a new feature to support define white list, that means only the products that defined in Singleton Service can work well to get translations and get supported language list. It is no impact for DateTimes / Numbers / Currencies / Plurals / Measurements / DateFields / RegionList.

By default, this feature is disabled.

This page will introduce the details about How to enable product white list in Singleton Service.

How to enable product white list in Singleton Service?
------------------

The steps:

1. To generate a Singleton Service build  or get a Singleton service build based on 0.3.0;

2. Create a JSON file named as `bundle.json`, and put it into the folder `.\l10n\bundles\`
The content format like:

```
{
    "Testing": ["1.0.0", "1.0.5"],
    "Testing2": ["1.0.0"]
}
```

