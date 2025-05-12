# About the component compiler

You use the component compiler to generate a SWC file from component source
files and other asset files such as images and style sheets. A SWC file is an
archive of components and other assets. For more information about SWC files,
see [About SWC files](../about-swc-files.md).

In some ways, the component compiler is similar to the application compiler. The
application compiler produces a SWF file from one or more MXML and ActionScript
files; the component compiler produces a SWC file from its input files. SWC
files are compressed files that contain a SWF file (library.swf), asset files,
and a catalog.xml file.

You use the component compiler to create the following kinds of assets:

Component libraries  
Component libraries are SWC files that contain one or more components that are
used by applications. SWC files also contain the namespace information that
describe the contents of the SWC file. For more information about component
libraries, see [About SWC files](../about-swc-files.md).

Runtime shared libraries (RSLs)  
RSLs are external shared assets that can be separately downloaded and cached on
the client. These shared assets are loaded by any number of applications at run
time. For more information on RSLs, see
[Runtime Shared Libraries](../../../application-architecture/runtime-shared-libraries/index.md).

Themes  
Themes are a combination of skins and Cascading Style Sheets (CSS). You use
themes to define the look and feel of an application built with Flex. For more
information on themes, see
[Styles and themes](../../../enhancing-the-user-interface/styles-and-themes.md).

You use the component compiler in the following ways:

Flash Builder Library Project compiler  
Flash Builder uses the component compiler when you create a Library Project.
(The application compiler is used for Flex Projects and ActionScript Projects).
For more information, see
[Using the Flash Builder component compiler](./about-the-application-compilers.md#using-the-flash-builder-application-compiler).

The compc command-line compiler  
You open the compc compiler from the command line to create a SWC file. For more
information, see
[Using the compc component compiler](../using-compc-the-component-compiler/).

The component compiler has many of the same options as the application
compilers, as described in
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).
The component compiler has additional options as described in
[About the component compiler options](../using-compc-the-component-compiler/about-the-component-compiler-options.md).

Like the application compiler, you can use the `load-config` option to point the
component compiler to a configuration file, rather than specify command-line
options or set the options in the Flex Compiler dialog box.

When you compile a SWC file, store the new file in a location that is not the
same as the source files. If both sets of files are accessible by Flex when you
compile your application, unexpected behavior can occur.

The SWC files that are produced by the component compilers do not require an
HTML wrapper because they are used as themes, RSLs, or component libraries that
are input to other compilers to create applications. You never deploy a SWC file
that users can request directly.

## Using the Flash Builder component compiler

You use the component compiler in Flash Builder to create SWC files. You do this
by setting up a Flex Library Project using the New Library Project command. You
add MXML and ActionScript components, style sheets, SWF files, and other assets
to the project.

To open the Flash Builder component compiler, select Project \> Build Project
for your Flex Library Project.

You edit the compiler settings by using the settings on the Project \>
Properties \> Flex Compiler dialog box. Using the Additional Compiler Arguments
field in this dialog box, you can set compiler options as if you were using the
command-line compiler. For information about the syntax for setting options in
the Flex Compiler dialog box, see
[About the command-line compilers](../about-the-command-line-compilers/index.md).

You can set the value of some options using the GUI controls. To set the
resource options in the Flex Library Build Path dialog box, select Project \>
Properties \> Flex Library Build Path.

Flash Builder does not expose a default configuration file to set compiler
options but you can create your own and pass it to the compiler with the
`load-config` option. For more information on setting compiler options with
configuration files, see
[About configuration files](../about-configuration-files/index.md).

## Using the compc component compiler

You use the compc command-line compiler to compile SWC files from MXML,
ActionScript, and other source files such as style sheets, images, and SWF
files.

You can open the compc compiler as a shell script and executable file for use on
Windows and UNIX systems. It is in the _flex_install_dir_/bin directory in Flex
SDK

To use the compc compiler, you should understand how to pass options and use
configuration files. For more information, see
[About the command-line compilers](../about-the-command-line-compilers/index.md).

The syntax of the compc compiler is as follows:

    compc [options] -include-classes class [...]

The default option for compc is `include-classes`. At least one of the
`include-` options is required.

To see a list of supported options for compc, you can use the ` help``list `
option, as the following example shows:

    compc -help list

The compc compiler uses the default compiler settings in the flex-config.xml
file. Like the application compiler, you can change these settings or use
another custom configuration file. Unlike the application compiler, however, the
component compiler does not support the use of default configuration files.

You cannot use the compc compiler to create a SWC file from a FLA file or other
file created in the Adobe® Flash® authoring environment.

You can also open the compc compiler with the `java` command on the command
line. For more information, see
[Invoking the command-line compilers with Java](../about-the-command-line-compilers/invoking-the-command-line-compilers-with-java.md).
