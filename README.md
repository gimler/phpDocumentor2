README
======

What is phpDocumentor?
----------------

phpDocumentor an application that is capable of analyzing your PHP source code and
DocBlock comments to generate a complete set of API Documentation.

Inspired by phpDocumentor and JavaDoc it continues to innovate and is up to date
with the latest technologies and PHP language features.

Features
--------

phpDocumentor sports the following:

* *PHP 5.3 compatible*, full support for Namespaces, Closures and more is provided.
* *Shows any tag*, some tags add additional functionality to phpDocumentor (such as @link).
* *Processing speed*, Zend Framework experienced an 80% reduction in processing time compared to phpDocumentor.
* *Low memory usage*, peak memory usage for small projects is less than 20MB, medium projects 40MB and large frameworks 100MB.
* *Incremental parsing*, if you kept the Structure file from a previous run you get an additional performance boost of up
  to 80% on top of the mentioned processing speed above.
* *Easy template building*, if you want to make a branding you only have to call 1 task and edit 3 files.
* *Basic command-line compatibility with phpDocumentor*, phpDocumentor is an application in its own right but the
  basic phpDocumentor arguments, such as --directory, --file and --target, have been adopted.
* *Two-step process*, phpDocumentor first generates a XML file with your application structure before creating the output.
  If you'd like you can use that to power your own tools or formatters!

Requirements
------------

phpDocumentor requires the following:

* PHP 5.3.2 or higher
* iconv/ext, http://php.net/manual/en/book.iconv.php (is enabled by default since PHP 5.0.0)
* The XSL extension, http://www.php.net/manual/en/book.xsl.php
* Graphviz (optional, used for generating Class diagrams)
* PEAR (optional, used for generating Class Diagrams or installing via PEAR)

**Note:**
If you do not want to install the PEAR or Graphviz dependency you are encouraged to generate your own template and make sure that it does not contain anything related to `Graph`.
An easier solution might be to edit `data/templates/responsive/template.xml` file and remove every line containing the word `Graph` but this will be undone with every upgrade of phpDocumentor.

Please see the documentation about creating your own templates for more information.

Installation
------------

There are 2 ways to install phpDocumentor:

1. Via PEAR (recommended)
2. Directly from source (Github)

_*Please note* that it is required that the installation path of phpDocumentor does not
contain spaces. This is a requirement imposed by an external library (libxml)_

### PEAR (recommended)

1. phpDocumentor is hosted on its own PEAR channel which can be discovered using the following command:

        $ pear channel-discover pear.phpdoc.org

2. After that it is a simple matter of invoking PEAR to install the application

        $ pear install phpdoc/phpDocumentor

### Directly from source (Github)

1. Download the latest released version from [Github](https://github.com/phpDocumentor/phpDocumentor2/tags) or
   if you feel really adventurous you can try the latest [unreleased](https://github.com/phpDocumentor/phpDocumentor2/tarball/develop).
2. Unzip the downloaded file to the intended destination location.
3. phpDocumentor comes without templates by default when manually installed, to install
   the default template call the template installer and install the `responsive`
   template.

        $ php {INSTALLATION_FOLDER}/bin/phpdoc.php template:install responsive -v 1.0.0

All other dependencies are included in the phpDocumentor package, so this is really it.
You might want to create a symbolic link or batch file from a location in your PATH
to make it easier to use but this is not required.

How to use phpDocumentor?
-------------------

The easiest way to run phpDocumentor is by running the following command when installed via PEAR:

    $ phpdoc run -d <SOURCE_DIRECTORY> -t <TARGET_DIRECTORY>

or when you did a manual installation:

    $ php {INSTALLATION_FOLDER}/bin/phpdoc.php run -d <SOURCE_DIRECTORY> -t <TARGET_DIRECTORY>

This command will parse the source code provided using the `-d` argument and
output it to the folder indicated by the `-t` argument.

phpDocumentor supports a whole range of options to configure the output of your documentation.
You can execute the following command, or check our website, for a more detailed listing of available command line options.

    $ phpdoc run -h

Configuration file(s)
---------------------

phpDocumentor also supports the use of configuration files (named phpdoc.xml or phpdoc.dist.xml by default).
Please consult the documentation to see the format and supported options.

Documentation
-------------

For more detailed information you can check our online documentation at [http://phpdoc.org/docs/](http://phpdoc.org/docs/).

Known issues
------------

1. Search does not work / is not available when accessing the documentation locally from Google Chrome.
   Google Chrome blocks access to local files (and thus the search index) using Javascript when working
   with local files (file://); it is not possible for us to fix this.
2. phpDocumentor must be installed in a path without spaces due to restrictions in libxml. The XSL transformation
   will throw all kinds of odd warnings if the path contains spaces.

Contact
-------

To come in contact is actually dead simple and can be done in a variety of ways.

* Twitter: [@phpDocumentor](http://twitter.com/phpdocumentor)
* Website: [http://www.phpdoc.org](http://www.phpdoc.org)
* IRC:     Freenode, #phpdocumentor
* Github:  [http://www.github.com/phpdocumentor/phpdocumentor2](http://www.github.com/phpdocumentor/phpdocumentor2)
* E-mail:  [mike.vanriel@naenius.com](mailto:mike.vanriel@naenius.com)
