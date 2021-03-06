AutoPkg BESEngine
=======

AutoPkgBESEngine is a collection of shared processors for [AutoPkg](https://github.com/autopkg/autopkg) used to automatically create and import software deployment tasks into a [IBM Endpoint Manager](http://www.ibm.com/software/tivoli/solutions/endpoint-manager/) console.

AutoPkgBESEngine.py     - AutoPkg Processor for BES (BigFix) XML Tasks and Fixlets

BESImporter.py          - AutoPkg Processor for importing tasks using the BigFix RESTAPI

BESUploader.py          - AutoPkg Processor for uploading files using the BigFix REST API

BESRelevanceProvider.py - AutoPkg Processor for retreiving relevance data for tasks

Installation
------------
***Python Requirements***

- lxml
- requests
- [besapi](https://github.com/hansen-m/besapi)

***The easy way...***

```
autopkg repo-add https://github.com/autopkg/hansen-m-recipes.git
autopkg install BESEngine

autopkg install QnA
```

***The hard way...***

Copy or symlink the BES processors (Code/*.py files) to /Library/AutoPkg/autopkglib.

You can specify your BES console settings directly in the recipes or set them globally:

```
defaults write com.github.autopkg BES_ROOTSERVER yourBESRootServer
defaults write com.github.autopkg BES_USERNAME yourAPIUserAccount
defaults write com.github.autopkg BES_PASSWORD yourAPIUserAccountPassword
```

A few related shared processors for using relevance and utilizing Windows recipes are available [here](https://github.com/autopkg/hansen-m-recipes/tree/master/SharedProcessors).

Discussion
----------

Discussion of the use and development of AutoPkg is [here](http://groups.google.com/group/autopkg-discuss).

If you would like to contact the maintainters directly please send an email to clcmac@psu.edu

If you have any questions on getting started we'd be happy to help. Or just let us know if you implement this project in your own organization.

Where can I find BigFix recipes?
----------

Penn State currently has over 100 BigFix recipes for commonly used software. Unfortunately, these recipes include many organization specific settings, file paths and naming conventions. We are in the process of cleaning up these recipes so they can be shared publicly.

We are also working on making it easier to share recipes by adding more flexibility for using recipe overrides so organizations can add their own specific customizations but still take advantage of the shared recipes and to share their own.

You can find example recipes under the "Examples" directory. If you'd like to work with us on getting a recipe for a specific piece of software or have any suggestions for making bigfix recipes easier to share please open an issue or send us an email at clcmac@psu.edu.

Known Issues
----------

- AutoPkgBESEngine only supports the generation of a single prefetch item, but additional prefetch lines can be hardcoded into the recipes.

- BESUploader requires a master operator account. Please vote for this IBM RFE - http://www.ibm.com/developerworks/rfe/execute?use_case=viewRfe&CR_ID=41378

- BESRelevanceProvider only supports a single relevance statement and stores the return value in a statically named variable.


License
----------

Copyright The Pennsylvania State University.
