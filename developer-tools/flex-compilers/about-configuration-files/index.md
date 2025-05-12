# About configuration files

Configuration files can be used by the command-line utilities and Flash Builder
compilers.

Flex includes a default configuration file named flex-config.xml. This
configuration file contains most of the default compiler settings for the
application and component compilers. You can customize this file or create your
own custom configuration file.

Flex SDK includes the flex-config.xml file in the _flex_install_dir_/frameworks
directory.

The Flash Builder compilers do not use a flex-config.xml file by default. The
default settings are stored internally. You can, however, create a custom
configuration file and pass it to the Flash Builder compilers by using the
`load-config` option. Flash Builder includes a copy of the flex-config.xml file
that you can use as a template for your custom configuration file. This file
located in the _flash_builder_install_dir_/sdks/_sdk_version_/frameworks
directory.

You can generate a configuration file with the current settings by using the
`dump-config` option, as the following example shows:

    mxmlc -dump-config myapp-config.xml

More Help topics

[Locating configuration files](./locating-configuration-files.md)

[Configuration file syntax](./configuration-file-syntax.md)
