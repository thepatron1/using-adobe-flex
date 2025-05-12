# About the application compilers

The application compilers create SWF files that are run in an Adobe™ Flash®
Player client or in an Adobe AIR™ application. The client can be a stand-alone
Flash Player or a Flash Player in a browser, which takes the form of an ActiveX
control for Microsoft Internet Explorer or a plug-in for Netscape-based
browsers.

Flash Builder project compiler  
The Flash Builder application compiler is opened by Flash Builder for Flex
Projects and ActionScript Projects. (The component compiler is used for Library
Projects.) It is similar in functionality to the mxmlc command-line compiler,
although the way you set options is different. You use this compiler to compile
Flash Builder projects that you will later deploy. For more information, see
[Using the Flash Builder application compiler](./about-the-application-compilers.md#using-the-flash-builder-application-compiler).

The mxmlc command-line compiler  
You open the mxmlc compiler from the command line to create a SWF file that you
then deploy to a website. Typically, you pass the name of the application's root
MXML file to the compiler. The output is a SWF file. For more information, see
[Using the mxmlc application compiler](../using-mxmlc-the-application-compiler/index.md).

The Flash Builder compiler and mxmlc compiler have similar sets of options.
These are described in
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).

You can compile applications that are written entirely in ActionScript and
contain no MXML. You can compile these "ActionScript-only" applications with the
Flash Builder and mxmlc compilers.

## Using the Flash Builder application compiler

You use the Flash Builder application compiler to create SWF files from MXML,
ActionScript, and other source files. You use this compiler to precompile SWF
files that you deploy later.

To open the Flash Builder application compiler, you select Project \> Build. The
Flash Builder application compiler is opened by Flash Builder for Flex Projects
and ActionScript Projects. (You use the component compiler for Library
Projects.)

To edit the compiler settings, use the settings on the Project \> Properties \>
Flex Compiler dialog box. For information on the compiler options, see
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).

The Flash Builder compiler has the same options as the mxmlc compiler. Some
options are implemented with GUI controls in the Flex Compiler dialog box. To
set the source path and library options, select Project \> Properties \> Flex
Build Path and use the Flex Build Path dialog box.

You can set the values of most options in the Additional Compiler Arguments
field by using the same syntax as on the command line. For information about the
command-line syntax, see
[About the command-line compilers](../about-the-command-line-compilers/index.md).

In the Additional Compiler Arguments field, you can substitute a path to the SDK
directory by using the `${flexlib}` token, as the following example shows:

    -include-libraries "${flexlib}/libs/automation.swc" "${flexlib}/libs/automation_agent.swc"

By default, Flash Builder exposes the compilation options through the project
properties. If you want to use a configuration file, you can create your own and
pass it to the compiler by using the `load-config` option. For more information
on setting compiler options with configuration files, see
[About configuration files](../about-configuration-files/index.md).

In addition to generating SWF files, the Flash Builder compiler also generates
an HTML wrapper that you can use when you deploy the new application. The HTML
wrapper includes the `<object>` and `<embed>` tags that reference the new SWF
file, as well as scripts that support history management and player version
detection. For more information about the HTML wrapper, see
[Creating a wrapper](../../../deploying-applications/creating-a-wrapper/index.md).

The Flash Builder application compiler uses incremental compilation by default.
For more information on incremental compilation, see
[About incremental compilation](../using-mxmlc-the-application-compiler/about-incremental-compilation.md).

## Using the mxmlc application compiler

You use the mxmlc command-line compiler to create SWF files from MXML, AS, and
other source files. You can open it as a shell script and executable file for
use on Windows and UNIX systems. You use this compiler to precompile
applications that you deploy later.

The command-line compiler is installed with Flex SDK. It is in the
_flex_install_dir_/bin directory in Flex SDK. The compiler is also included in
the default Flash Builder installation, in the
_flash_builder_install_dir_/sdks/_sdk_version_/bin directory.

To use the mxmlc utility, you should understand its syntax and how to use
configuration files. For more information, see
[About the command-line compilers](../about-the-command-line-compilers/index.md).

The basic syntax of the mxmlc utility is as follows:

    mxmlc [options] target_file

The default option is the target file to compile into a SWF file, and it is
required to have a value. If you use a space-separated list as part of the
options, you can terminate the list with a double hyphen before adding the
target file; for example:

    mxmlc -option arg1 arg2 arg3 -- target_file.mxml

To see a list of options for mxmlc, you can use the ` help``list ` option, as
the following example shows:

    mxmlc -help list

To see a list of all options available for mxmlc, including advanced options,
you use the following command:

    mxmlc -help list advanced

The default output of mxmlc is _filename_.swf, where _filename_ is the name of
the root application file. The default output location is in the same directory
as the target, unless you specify an output file and location with the `output`
option.

The mxmlc command-line compiler does not generate an HTML wrapper. You must
create your own wrapper to deploy a SWF file that the mxmlc compiler produced.
The wrapper is used to embed the SWF object in the HTML tag. It includes the
`<object>` and `<embed>` tags, as well as scripts that support Flash Player
version detection and history management. For information about creating an HTML
wrapper, see
[Creating a wrapper](../../../deploying-applications/creating-a-wrapper/index.md).

The mxmlc utility uses the default compiler settings in the flex-config.xml
file. This file is in the _flex_sdk_dir_/frameworks/ directory. You can change
the settings in this file or use another custom configuration file. For more
information on using configuration files, see
[About configuration files](../about-configuration-files/index.md).

The mxmlc compiler is highly customizable with a large set of options. For
information on the compiler options, see
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).

You can also open the mxmlc compiler with the `java` command on the command
line. For more information, see
[Invoking the command-line compilers with Java](../about-the-command-line-compilers/invoking-the-command-line-compilers-with-java.md).
