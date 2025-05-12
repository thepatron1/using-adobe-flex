# Adding nonsource classes

You often include noncompiled (or nonsource) files with your applications. A
_nonsource_ file is a class or resource (such as a style sheet or graphic) that
is not compiled but is included in the SWC file for other classes to use. For
example, a font file that you embed or a set of images that you use as graphical
skins in a component's style sheet should not be compiled but should be included
in the SWC file. These are classes that you typically do not use the `[Embed]`
syntax to link in to your application.

Use the `include-file` option to define nonsource files in a SWC file.

The syntax for the `include-file` option is as follows:

    -include-file name path

The _name_ argument is the name used to reference the embedded file in your
applications. The _path_ argument is the current path to the file in the file
system.

When you use the `include-file` option, you specify both a name and a filepath,
as the following example shows:

    compc -include-file logo.gif c:/images/logo/logo1.gif ...

In a configuration file, these options appear as the following example shows:

    <compiler>
    	<output>c:/jrun4/servers/flex/flex/WEB-INF/flex/user_classes/Combo.swc</output>
    </compiler>
    <include-file>
    	<name>logo.gif</name>
    	<path>c:/images/logo/logo1.gif</path>
    </include-file>
    <include-classes>
    	<class>asbutton.MyButton</class>
    <include-classes>

Each name that you assign to a resource must be unique because the name becomes
a global variable.

You cannot specify a list of files with the `include-file` option. So, you must
add a separate `include-file` option for each file that you include, as the
following command-line example shows:

    compc -include-file file1.jpg ../images/file1.jpg -include-file file2.jpg ../images/file2.jpg -- -output MyFile.swc

If you want to add many resources to the SWC file, consider using a
configuration file rather than listing all the resources on the command line.
For an example of a configuration file that includes multiple resources in a SWC
file, see
[Styles and themes](../../../enhancing-the-user-interface/styles-and-themes.md).

In general, specify a file extension for files that you include with the
`include-file` option. In some cases, omitting the file extension can lead to a
loss of functionality. For example, if you include a CSS file in a theme SWC
file, you must set the name to be \*.css. When Flex examines the SWC file, it
applies all CSS files in that SWC file to the application. CSS files without the
CSS extension are ignored.
