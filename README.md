# web-cctray

*Web-based dashboard for cctray.xml files*

[![Master Build Status](https://secure.travis-ci.org/tecnickcom/web-cctray.png?branch=master)](https://travis-ci.org/tecnickcom/web-cctray?branch=master)

[![Donate via PayPal](https://img.shields.io/badge/donate-paypal-87ceeb.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&currency_code=GBP&business=paypal@tecnick.com&item_name=donation%20for%20web-cctray%20project)
*Please consider supporting this project by making a donation via [PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&currency_code=GBP&business=paypal@tecnick.com&item_name=donation%20for%20web-cctray%20project)*

* **category**    Web Application
* **author**      Nicola Asuni <info@tecnick.com>
* **copyright**   2013-2017 Nicola Asuni - Tecnick.com LTD
* **license**     MIT (see LICENSE)
* **link**        https://github.com/tecnickcom/web-cctray

## Description

This web application displays the build status of projects on a continuous integration server by parsing the `cctray.xml` file.

This project can be used directly by opening the `index.html` file in the *src* directory, or it can be packaged and minimized using the tools described below.

### Query parameters:

* **c** : can be used to specify an alternative configuration file name, excluding the ".json" extension.
* **d** : can be used to specify the configured dashboard to display, otherwise all the dashboards will be displayed in turn.
* **a** : can be used to display only the pipelines with the selected activity status. Valid values are: all, Sleeping, Building, CheckingModifications, Pending.
* **s** : can be used to display only the pipelines with the selected build status. Valid values are: all, Success, Failure, Exception, Unknown.

For example: \
`http://example.com/web-cctray/index.html?c=alternative_config&d=DashboardName`


## Configuration

Copy, rename and edit the `src/config/config.example.json` to `src/config/config.json` file.

### Configuration fields:

* **refresh** : Number of seconds to wait before refreshing the page.
* **dashboard** : Array of dashboards. It is possible to define multiple dashboards.
    * **name** : Name of the CI/CD pipeline as reported by cctray.xml.
    * **url** : URL of the cctray.xml file, for example: http://username:password@example.com/cctray.xml
    * **access** : String containing "user:password" for Basic HTTP Authentication.
    * **fontratio** : Font ratio relative to monitor size.
    * **ngrid** : Dashboard layout in rows and columns.


## Supported CI/CD systems

The following is a list of CI/CD systems that provides a cctray.xml file:

* [Buddybuild](https://www.buddybuild.com)
* [CircleCI](https://circleci.com)
* [CruiseControl](http://cruisecontrol.sourceforge.net)
* [CruiseControl.NET](http://www.cruisecontrolnet.org)
* [CruiseControl.rb](http://cruisecontrolrb.thoughtworks.com)
* [GoCD](http://www.go.cd)
* [GreenhouseCI](http://greenhouseci.com)
* [Hudson](http://hudson-ci.org)
* [Jenkins](http://jenkins-ci.org)
* [Semaphore](https://semaphoreapp.com)
* [Snap CI](https://snap-ci.com)
* [TeamCity](https://www.jetbrains.com/teamcity)
* [Travis](https://travis-ci.org)


## Packages

Pre-built packages are available at:

* DEB : https://bintray.com/tecnickcom/deb/web-cctray
* RPM : https://bintray.com/tecnickcom/rpm/web-cctray

The application is installed by default in /usr/share/web-cctray


## Getting started (for developers)

This project include a Makefile that allows you to automate common operations in a Debian/Ubuntu enviromnent.

To see all available options:
```
make help
```
To build the project (requires node):
```
make deps build
```
