# Adding utility classes

You can add any classes that you want to use in your applications to a SWC file.
These classes do not have to be components, but are often files that components
use. They are classes that might be used at run time and, therefore, are not
checked by the compiler. For example, your components might use a library of
classes that perform mathematical functions, or use a custom logging utility.
This documentation refers to these classes as _utility classes_. Utility classes
are not exposed as MXML tags.

To add utility classes to a SWC file, you use the `include-sources` option. This
option lets you specify a path to a class file rather than the class name, or
specify an entire directory of classes.

The following command-line example adds the FV_calc.as and FV_format.as utility
classes to the SWC file:

    compc -source-path .
        -output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MySwc.swc
        -include-sources FV_classes/FV_format.as FV_classes/FV_calc.as
        -include-classes asbutton.MyButton

In a configuration file, these options appear as the following example shows:

    <compiler>
        <source-path>
            <path-element>.</path-element>
        </source-path>
        <output>c:/jrun4/servers/flex/flex/WEB-INF/flex/user_classes/        MySwc.swc</output>
    </compiler>
    <include-classes>
        <class>asbutton.MyButton</class>
    </include-classes>
    <include-sources>
        <path-element>FV_classes/FV_format.as</path-element>
        <path-element>FV_classes/FV_calc.as</path-element>
    <include-sources>

When specifying files with the `include-sources` option, you must give the full
filename (for example, FV_calc.as instead of FV_calc) because the file is not a
component. If you use this option to include MXML components that are in a
non-default package, you must include the source folder in the source path.

You can also provide a directory name to the `include-sources` option. In this
case, the compiler includes all files with an MXML or AS extension, and ignores
all other files.

Classes that you add with the `include-sources` option can be accessed from the
generic namespace in your applications. To use them, you need to add the
following code in your application tag:

    xmlns:local="*"

You can then use them as tags; for example:

    <local:FV_calc id="calc" rate=".0125" nper="12" pmt="100" pv="0" type="1"/>
