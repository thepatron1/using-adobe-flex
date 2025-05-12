# Using abbreviated option names

In some cases, the command-line help shows an option with dot-notation syntax;
for example, `source-path` is shown as `compiler.source-path`. This notation
indicates how you would set this option in a configuration file. On the command
line, you can specify the option with only the final node, `source-path`, as
long as that node is unique, as the following example shows:

    mxmlc -source-path . c:/myclasses/ -- foo.mxml

For more information about using configuration files to store command-line
options, see [About configuration files](../about-configuration-files/index.md).

Some compiler options have aliases. _Aliases_ provide shortened variations of
the option name to make command lines more readable and less verbose. For
example, the alias for the `output` option is `o`. You can view a list of
options by their aliases by using the following command:

    mxmlc -help list aliases

or

    mxmlc -help list advanced aliases

You can also see the aliases in the verbose help output by using the following
command:

    mxmlc -help list details
