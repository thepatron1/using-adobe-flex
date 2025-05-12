# About SWC files

A _SWC_ file is an archive file, sometimes also referred to as a class library,
for components and other assets. SWC files contain a SWF file and a catalog.xml
file, in addition to properties files and other uncompiled assets such as CSS
files. The SWF file implements the compiled component or group of components and
includes embedded resources as symbols. An application extracts the SWF file
from a SWC file. It uses the SWF file's contents when the application refers to
resources in that SWC file. The catalog.xml file lists of the contents of the
component package and its individual components.

In most cases, the symbols defined in the SWF file that are referenced by the
application are embedded in the application at compile-time. This is known as
static linking. The application compiler only includes those classes that are
used by your application, and dependent classes, in the final SWF file.

You can also dynamically link the contents of SWC files. Dynamic linking is when
the entire SWF file is loaded at run time. To achieve dynamic linking of the SWF
file, you must use the SWC file as a Runtime Shared Library, or RSL. For more
information, see
[Runtime Shared Libraries](../../application-architecture/runtime-shared-libraries/index.md).

SWC files make it easy to exchange components and other assets among Flex
developers. You need only exchange a single file, rather than the MXML or
ActionScript files and images and other resource files. The SWF file in a SWC
file is compiled, which means that the code is loaded efficiently and it is
hidden from casual view. Also, compiling a component as a SWC file can make
namespace allocation an easier process.

You can package and expand SWC files with tools that support the PKZip archive
format, such as WinZip or jar. However, do not manually change the contents of a
SWC file, and do not try to run the SWF file that is in a SWC file in Flash
Player.

You typically create SWC files by using compc, the command-line component
compiler.

You can also save SWC files as open directories rather than archived files. This
gives you easier access to the contents of the SWC file. You create an open
directory SWC by setting the `directory` option to `true`. This is typically
only used when you create a custom RSL because RSLs require that you deploy the
SWF file with your application.

The properties files inside SWC files are uncompiled text files in UTF-8 format.
They are used as resource bundles for localization of applications. Within the
SWC file, they are stored in the /locale/_locale_string_ directory, where
`locale_string` is something like en_US or fr_FR. For more information, see
[Localization](../../enhancing-usability/localization.md).

## Distributing SWC files

After you generate a SWC file, you can use it in your applications.

You can also copy SWC files to a directory specified by the `library-path`
compiler option. You must store SWC files at the top level of the user_classes
directory or the directory specified by the `library-path`. You cannot store SWC
files in subdirectories.

To use a SWC file when compiling components or applications from the command
line or from within Flash Builder, you specify the location of the SWC file with
the `library-path` compiler option.

Note: Do not store custom components or classes in the
flex_root/WEB-INF/flex/libs directory. This directory is for Adobe classes and
components.

## Using components in SWC files

If a component in a SWC file does not have a namespace, you can add a generic
namespace identifier in your `<s:Application>` tag to use the component, as the
following example shows:

    <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
    	xmlns:s="library://ns.adobe.com/flex/spark"
    	xmlns:mx="library://ns.adobe.com/flex/mx"
    	xmlns:a="*">

If the component has a package name as part of its namespace, you must do one of
the following:

1.  Add the package name to the namespace declaration in the `<s:Application>`
    tag; for example:

        <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
        	xmlns:s="library://ns.adobe.com/flex/spark"
        	xmlns:mx="library://ns.adobe.com/flex/mx"
        	xmlns:but="mycomponents.*">

2.  Create a manifest file and recompile the SWC file. You pass the manifest
    file to the compc compiler by using the `namespace` option. In the
    `<s:Application>` tag, you specify only the unique namespace URI that you
    used with compc. For more information on specifying a namespace for the
    component, see
    [Compiling components using namespaces](./using-compc-the-component-compiler/compiling-components-using-namespaces/index.md).
