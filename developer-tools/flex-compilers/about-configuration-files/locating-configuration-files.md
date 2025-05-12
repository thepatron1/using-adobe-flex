# Locating configuration files

You can specify the location of a configuration file by using the `load-config`
option. The target configuration file can be the default flex-config.xml file,
or it can be a custom configuration file. The following example loads a custom
configuration file:

    compc -load-config=myconfig.xml

If you specify the filename with the `+=` operator, your loaded configuration
file is used _in addition to_ and not instead of the flex-config.xml file:

    compc -load-config+=myconfig.xml

With the mxmlc compiler, you can also use a local configuration file. A _local
configuration file_ does not require you to point to it on the command line.
Rather, Flex examines the same directory as the target MXML file for a
configuration file with the same name (one that matches the
_filename_-config.xml filename). If it finds a file, it uses it in conjunction
with the flex-config.xml file. You can also specify a configuration file by
using the `load-config` option with the `+=` operator.

For example, if your application's top-level file is called MyApp.mxml, the
compiler first checks for a MyApp-config.xml file for configuration settings.
With this feature, you can easily compile multiple applications using different
configuration options without changing your command-line options or your
flex-config.xml file.

Options in the local configuration file take precedence over options set in the
flex-config.xml file. Options set in a configuration file that the `load-config`
option specify take precedence over the local configuration file. Command-line
settings take precedence over all configuration file settings. For more
information on the precedence of compiler options, see
[About option precedence](../about-option-precedence.md).
