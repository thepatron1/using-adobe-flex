# Viewing errors and warnings

You can use the compiler options to specify what level of warnings and errors to
view. Also, you can set levels of logging with the compiler options.

## Viewing warnings and errors

There are several options that let you customize the level of warnings and
errors that are displayed by the Flex compilers, including the following:

- `show-actionscript-warnings`

- `show-binding-warnings`

- `show-invalid-css-property-warnings`

- `show-shadowed-device-font-warnings`

- `show-unused-type-selector-warnings`

- `strict`

- `warnings`

To disable all warnings, set the `warnings` option to `false`.

The `show-actionscript-warnings` option displays compiler warnings for the
following situations:

1.  Situations that are probably not what the developer intended, but are still
    legal; for example:

        if (a = 10)                             // Did you really want '==' instead of '='?
        if (b == NaN)                             // Any comparison with NaN is always false.
        var b;                            // Missing type declaration.

2.  Usage of deprecated or removed ActionScript 2.0 APIs.

3.  Situations where APIs behave differently in ActionScript 2.0 than in
    ActionScript 3.0.

You can customize the types of warnings displayed by using options that begin
with _warn_ (for example, `warn-constructor-return-values` and
`warn-bad-type-cast`). A complete list of warnings are available in the advanced
command-line help or in the flex-config.xml file.

The `strict` option enforces typing and reports run-time verifier errors at
compile time. This option assumes that definitions are not dynamically redefined
at run time, so these checks can be made at compile time. It displays errors for
conditions such as undefined references, const and private violations, argument
mismatches, and type checking.

The `show-binding-warnings` option displays warnings when Flash Player cannot
detect changes to bound properties.

## About deprecation

In some cases, Flex functionality has been deprecated. Deprecated features and
properties have the following characteristics:

- Generate compiler warnings.

- Continue to work in Flex 4.x.

- Will be removed from the product in a future major release.

The command-line compilers report deprecation warnings by default. You can
suppress deprecation warnings by setting the `show-deprecation-warnings` option
to `false`.

In some cases, deprecated functionality does not work as expected unless you
instruct the compiler to use an earlier version of the compiler with the
`compatibility-version` compiler argument. For example, to use functionality
that was deprecated since Flex 3, you could use the following command-line
compiler argument:

    -compatibility-version=3.0.0

Possible values for this compiler argument are defined as constants in the
[FlexVersion](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/core/FlexVersion.html)
class. For more information on using this compiler argument, see
[Backward compatibility](../versioning/backward-compatibility.md).

You can use the `[Deprecated]` metadata tag to deprecate your own classes and
class elements. For more information, see
[Deprecated metadata tag](../../custom-components/metadata-tags-in-custom-components/metadata-tags.md#deprecated-metadata-tag).

## About logging

Errors and warnings are reported differently, depending on which compiler you
are using.

The mxmlc and compc command-line compilers send error and warning messages to
the standard output. You can redirect this output by using the redirector (\>).

Flash Builder displays error and warning messages in the Problems tab.
