# Configuration file syntax

You store values in a configuration file in XML blocks, which follow a specific
syntax. In general, the tags you use match the command-line options.

## About the root tag

The root tag of the default configuration file, flex-config.xml, is
`<flex-config>`. If you write a custom configuration file, it must also have
this root tag. Compiler configuration files must also have an XML declaration
tag, as the following example shows:

    <?xml version="1.0"?>
    <flex-config>

You must close the `<flex-config>` tag as you would any other XML tag. All
compiler configuration files must be closed with the following tag:

    </flex-config>

In general, the second tag in a configuration file is the `<compiler>` tag. This
tag wraps most compiler options. However, not all compiler options are set in
the `<compiler>` block of the configuration file.

Tags that you must wrap in the compiler block are prefixed by `compiler` in the
help output (for example, `compiler.services`). If the option uses no
dot-notation in the help output (for example, `include-file`), it is a tag at
the root level of the configuration file, and the entry appears as follows:

    <compiler>
    ...
    </compiler>
    <include-file>
        <name>logo.gif</name>
        <path>c:/images/logo/logo1.gif</path>
    </include-file>

In some cases, options have multiple parent tags, as with the fonts options,
such as `compiler.fonts.managers` and `compiler.fonts.languages.language`. Other
options that require parent tags when added to a configuration file include the
`frames.frame` option and the metadata options. The following sections describe
methods for determining the syntax.

## Getting the configuration file tags

Use the `help list` option of the command-line compilers to get the
configuration file syntax of the compiler options; for example:

    mxmlc -help list advanced

The following is the entry for the `source-path` option:

    -compiler.source-path [path-element][...]

This indicates that in the configuration file, you can have one or more
`<path-element>` child tags of the `<source-path>` tag, and that `<source-path>`
is a child of the `<compiler>` tag. The following example shows how this should
appear in the configuration file:

    <compiler>
        <source-path>
            <path-element>.</path-element>
            <path-element>c:/myclasses/</path-element>
        </source-path>
    </compiler>

## Understanding leaf nodes

The help output uses dot-notation to separate child tags from parent tags, with
the right-most entry being known as the _leaf node_. For example, `-tag1.tag2`
indicates that `<tag2>` should be a child tag of `<tag1>`.

Angle brackets (`< >`) or square brackets (`[ ]`) that surround an option
indicate that the option is a leaf node.

Square brackets indicate that there can be a list of one or more parameters for
that option.

If the leaf node of a tag in the angle bracket is unique, you do not have to
specify the parent tags in the configuration file. For example, the help usage
shows the following:

    compiler.fonts.managers [manager-class][...]

You can specify the value of this option in the configuration file, as the
following example shows:

    <compiler>
        <fonts>
            <managers>
                <manager-class>flash.fonts.JREFontManager</manager-class>
            </managers>
        </fonts>
    </compiler>

However, the `<manager-class>` leaf node is unique, so you can set the value
without specifying the `<fonts>` and `<managers>` parent tags, as the following
example shows:

    <compiler>
        <manager-class>flash.fonts.JREFontManager</manager-class>
    </compiler>

If the help output shows multiple options listed in angle brackets, you set the
values of these options at the same level inside the configuration file and do
not make them child tags of each other. For example, the usage for default-size
(`default-size <width> <height>`) indicates that the default size of the
application is set in a configuration file, as the following example shows:

    <default-size>
        <height>height_value</height>
        <width>width_value</width>
    </default-size>

## Using tokens

You can pass custom token values to the compiler using the following syntax:

    +token_name=value

In the configuration file, you reference that value using the following syntax:

    ${token_name}

You can use the `@Context` token in your configuration files to represent the
context root of the application. You can also use the `${flexlib}` token to
represent the frameworks directory. This is useful if you set up your own
configuration and are not using the default `library-path` settings.

The default value of the `${flexlib}` token is
_`application_home`_`\frameworks`.

## Appending values

In a configuration file, you can specify the `append` attribute of any tag that
takes a list of arguments. Set this attribute to `true` to indicate that the
values should be appended to the option rather than replace it. The default
value is `false`.

Setting the `append` attribute to `true` lets you compound the values of options
with multiple configuration files. The following example appends two entries to
the `library-path` option:

    <library-path append="true">
        <path-element>/mylibs</path-element>
        <path-element>/myotherlibs</path-element>
    </library-path>
