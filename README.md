## sqlcl-package for Debian and derivatives

**`sqlcl-package`** is a small script that will build a [_Debian_](http://www.debian.org) [_package_](http://www.wikipedia.org/wiki/Deb_%28file_format%29) from [_Oracle_](http://www.oracle.com)_'s_ [_SQL Developer Command-Line (SQLcl)_](http://www.oracle.com/technetwork/developer-tools/sqlcl/overview/).

This utility makes it possible to build a _Debian_ package of _Oracle SQL Developer Command-Line_. The _Oracle SQL Developer Command-Line_ program is governed by the copyright holder (_Oracle USA, Inc._), so you may be limited as to what you can do with the resulting package (i.e. no redistribution, etc). This utility will simply help you create the _Debian_ package, it is your responsibility to use the resulting package acordingly with the [_OTN license_](http://www.oracle.com/technetwork/licenses/sqldev-license-152021.html), a copy of which is included in the created package, that you must agree on when downloading the source.

This utility will require you to download the **architecture independent** archive from [_\<http://www.oracle.com/technetwork/developer-tools/sqlcl/overview/\>_](http://www.oracle.com/technetwork/developer-tools/sqlcl/overview), identified as "**_Oracle SQL Developer Command-Line for All Platforms_**", to create the _Debian_ package from.

<hr width="40%">

<u>The <em>Debian Package</em> <strong><em>sqlcl-package</em></strong></u>

In order to run _Oracle SQL Developer Command-Line_ you'll need a working [_JRE_](http://www.wikipedia.org/wiki/JRE). The minimum _JRE_ you should use is [_1.8_](http://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html) (_JRE8.0_).

There are several ways to obtain a **compatible** _JRE_:
- install [_`default-jre`_](http://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=default-jre) (java), making sure it depends, _at least_, on the minimum required _JRE_ version
- install one of the required [_`openjdk-8-jre`_](http://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=openjdk-8-jre) or [_`openjdk-9-jre`_](http://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=openjdk-9-jre) (java)
- install the meta-package _`java-runtime`_, making sure that it installs, _at least_, the minimum required _JRE_ version as dependency
- install one of the meta-packages _`java8-runtime`_ or _`java9-runtime`_, making sure that it installs, _at least_, the minimum required _JRE_ version as dependency
- download and run the installer for the version you wish to install from _Oracle_ [_&lt;http://www.oracle.com/technetwork/java/javase/downloads/&gt;_](http://www.oracle.com/technetwork/java/javase/downloads/)
- install [_`java-package`_](http://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=java-package) (contrib/misc) and generate a _Debian_ package from the above installer

After installing a **compatible** _JRE_ simply launch _SQL Developer Command-Line_ by invoking either `sqlcl` (**the recommended way**), `sqlcl.standalone` or `sql.[`_`upstream version`_`].standalone`. The _JRE_ will be automatically detected and used as long as properly installed.

<hr width="40%">

### **Version History**

##### [Version 0.1.0](https://github.com/lazarusllong/sqlcl-package/releases/tag/0.1.0):
- **changelog:**
  - Initial Release (Closes: [**#882113**](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=882113), [**#882115**](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=882115))
  - Due to a conflicting name with content of package [_`parallel`_](http://packages.debian.org/search?searchon=names&exact=1&suite=all&section=all&keywords=parallel) the upstream binary `sql` will be renamed. Multiple versions can coexist so `sql.[`_`upstream version`_`]` will invoke a specific version of _Oracle SQL Developer Command-Line_, `sql.[upstram version]` will invoke either the _standalone_ or _bundled_ _Oracle SQL Developer Command-Line_ version (in this order), while `sqlcl` (**the recommended way**) and `sqlcl.standalone` take advantage of _Debian_'s `alternatives` system and, when left in auto mode, will always invoke the highest version installed.
- **downloads:**
  - [**`sqlcl-package_0.1.0_all.deb`**](https://github.com/lazarusllong/sqlcl-package/releases/download/0.1.0/sqlcl-package_0.1.0_all.deb) (_binary package_)
  - [`sqlcl-package_0.1.0.dsc`](https://github.com/lazarusllong/sqlcl-package/releases/download/0.1.0/sqlcl-package_0.1.0.dsc) (_source description file_)
  - [`sqlcl-package_0.1.0.tar.xz`](https://github.com/lazarusllong/sqlcl-package/releases/download/0.1.0/sqlcl-package_0.1.0.tar.xz) (_source code archive_)
