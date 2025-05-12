# Command-line syntax

The mxmlc and compc compilers take many options. The options are listed in the
help which you can view with the `help` option, as the following example shows:

    mxmlc -help

This displays a menu of choices for getting help. The most common choice is to
list the basic configuration options:

    mxmlc -help list

To see advanced options, use the `list advanced` option, as the following
example shows:

    mxmlc -help list advanced

To see a list of entries whose names or descriptions include a particular
String, use the following syntax:

    mxmlc -help pattern

The following example returns descriptions for the `external-library-path`,
`library-path`, and `runtime-shared-libraries` options:

    mxmlc -help list library

For a complete description of mxmlc options, see
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).
For a complete description of compc options, see
[About the component compiler options](../using-compc-the-component-compiler/about-the-component-compiler-options.md).

Many command-line options, such as `show-actionscript-warnings` and
`accessible`, have `true` and `false` values. You specify these values by using
the following syntax:

    mxmlc -accessible=true -show-actionscript-warnings=true

Some options, such as `source-path`, take a list of one or more options. You can
see which options take a list by examining the help output. Square brackets
(`[ ]`) that surround options indicate that the option can take a list of one or
more parameters.

You can separate each entry in a list with a space or a comma. The syntax is as
follows:

    -var val1 val2

or

    -var=val1, val2

If you do not use commas to separate entries, you terminate a list by using a
double hyphen, as the following example shows:

    -var val1 val2 -- -next_option

If you use commas to separate entries, you terminate a list by not using a comma
after the last entry, as the following example shows:

    -var=val1, val2 -next_option

You can append values to an option using the += operator. This adds the new
entry to the end of the list of existing entries rather than replacing the
existing entries. The following example adds the c:/myfiles directory to the
`library-path` option:

    mxmlc -library-path+=c:/myfiles
