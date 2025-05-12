# About option precedence

You can set the same options in multiple places and the Flex compilers use the
value from the source that has the highest precedence.

If you do not specify an option on the command line, the compilers check for a
`load-config` option and get the value from that file.

When using the mxmlc compiler, Flex checks to see if there is an
_app_\__name_-config.xml file in the same directory as the target MXML file.
This is known as the local configuration file and is described in
[Locating configuration files](./about-configuration-files/locating-configuration-files.md).
The syntax and structure of local configuration files are the same as with the
flex-config.xml file.

If no `load-config` option is specified, the compilers check for the
flex-config.xml file. The compilers look for the flex-config.xml file in the
/frameworks directory. The following location is the default:

    {flex_root}/frameworks

Most options have a default value that the compilers use if the option is not
set in any of the other ways.

The following table shows the possible sources of options for each compiler. The
table also shows the order of precedence for each option. The options set using
the method described in a lower row take precedence over the options set using
the methods described in a higher row.

| Compiler options                                   | Flash Builder | mxmlc | compc |
| -------------------------------------------------- | ------------- | ----- | ----- |
| Default settings                                   | Yes           | No    | No    |
| flex-config.xml                                    | No            | Yes   | Yes   |
| Local configuration file                           | No            | Yes   | No    |
| Configuration file specified by load-config option | Yes           | Yes   | Yes   |
| Command-line option                                | No            | Yes   | Yes   |
| Options panel                                      | Yes           | No    | No    |

You can mix and match the source of the compiler options. For example, you can
specify a custom configuration file with the `load-config` option, and also set
additional options on the command line.

You can also use multiple configuration files. You can chain them by using the
`+=` operator with the `load-config` option. If you specify a configuration file
with this option, the compilers also look for the flex-config.xml and local
(_appname_-config.xml) configuration files.
