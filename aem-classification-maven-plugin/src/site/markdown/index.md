Introduction
-----------

This Maven Plugin allows to generate a classification map from a running
AEM instance. The classification map contains information about [content classifications][1] as well as deprecated resource types.

The map can be used together with the [FileVault AEM Classification Validator][2].

Prepare AEM Server
----------
The AEM instance needs to have several [query indices][3] in place for this plugin to work:

1. property index limited to properties jcr:primaryType and jcr:mixinTypes for node types granite:FinalArea, granite:PublicArea, granite:InternalArea and granite:AbstractArea
1. property index for properties cq:deprecated for any node type)

There is a package containing the relevant indices called [aem-classification-search-index-package][4].

Usage
---------

The only goal can be used without a Maven project like this

```
mvn biz.netcentric.filevault.validator:aem-classification-maven-plugin:1.0.0-SNAPSHOT:download-content-classification
```

[1]: https://docs.adobe.com/content/help/en/experience-manager-65/deploying/upgrading/sustainable-upgrades.html#content-classifications
[2]: https://github.com/Netcentric/aem-classification/tree/master/aem-classification-validator
[3]: https://jackrabbit.apache.org/oak/docs/query/property-index.html
[4]: https://github.com/Netcentric/aem-classification/tree/master/aem-classification-search-index-package