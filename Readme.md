# AEM Easy Content Upgrade (AECU)

AECU simplifies content migrations by executing migration scripts during package installation. It is built on top of [Groovy Console](https://github.com/OlsonDigital/aem-groovy-console).


Features:

* GUI to run scripts and see history of runs
* Run mode support
* Fallback scripts in case of errors
* Extension of Groovy Console bindings
* Service API
* Health Checks

Table of contents
1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Execution of Migration Scripts](#execution)
4. [History of Past Runs](#history)
5. [Extension to Groovy Console](#groovy)
6. [JMX Interface](#jmx)
7. [Health Checks](#healthchecks)
8. [License](#license)


<a name="requirements"></a>

# Requirements

AECU requires Java 8 and AEM 6.3 or above. Groovy Console can be installed manually if [bundle install](#bundleInstall) is not used.

<a name="installation"></a>

# Installation

TODO

<a name="bundleInstall"></a>

## Bundle Installation

To simplify installation we provide a bundle package that already includes the Groovy Console. This makes sure there are no compatibility issues.

TODO


<a name="execution"></a>

# Execution of Migration Scripts

TODO

<a name="history"></a>

# History of Past Runs

You can find the history in AECU's tools menu.

<img src="docs/images/tools.png">

The history shows all runs that were executed via package install hook, manual run and JMX. It will not display scripts that were executed directly via Groovy Console.

<img src="docs/images/historyOverview.png">

You can click on any run to see the full details. This will show the status for each script. You can also see the output of all scripts.

<img src="docs/images/historyDetails.png">

<a name="groovy"></a>

# Extension to Groovy Console

TODO

<a name="jmx"></a>

# JMX Interface

<img src="docs/images/jmx.png">

AECU provides JMX methods for executing scripts and reading the history. You can also check the version here.

## Execute

This will execute the given script or folder. If a folder is specified then all files (incl. any subfolders) are executed. AECU will respect runmodes during execution.

Parameters:
 * Path: file or folder to execute

## GetHistory

Prints the history of the specified last runs. The entries are sorted by date and start with the last run.

Parameters:
 * Start index: starts with 0 (= latest history entry)
 * Count: number of entries to print

## GetFiles

This will print all files that are executable for a given path. You can use this to check which scripts of a given folder would be executed.

Parameters:
* Path: file or folder to check


<a name="healthchecks"></a>

# Health Checks

Health checks show you the status of AECU itself and the last migration run.
You can access them on the [status page](http://localhost:4502/libs/granite/operations/content/healthreports/healthreportlist.html/system/sling/monitoring/mbeans/org/apache/sling/healthcheck/HealthCheck/aecuHealthCheckmBean).
For the status of older runs use AECU's history page.

<img src="docs/images/healthCheck.png">

<a name="license"></a>

# License

The AC Tool is licensed under the [GNU GENERAL PUBLIC LICENSE - v 3](LICENSE).
