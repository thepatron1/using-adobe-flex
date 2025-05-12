# Compiling stand-alone components and classes

In many cases, you have one or more components that you use in your
applications, but you do not have them in a package structure. You want to be
able to use them in the generic namespace ("\*") inside your applications. In
these cases, you use the `include-classes` option to add the components to your
SWC file.

The following command-line example compiles two MXML components, Rotation.as and
RotationInstance.as, into a single SWC file:

    compc -source-path .
    	-output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/RotationClasses.swc
    	-include-classes rotationClasses.Rotation rotationClasses.RotationInstance

The rotationClasses directory is a subdirectory of the current directory, which
is in the source path. The SWC file is output to the user_classes directory, so
the new components require no additional configuration to be used in a server
environment.

You use the `include-classes` option to add components to the SWC file. You use
just the class name of the component and not the full filename (for example,
MyComponent rather than MyComponent.as). Use dot-notation to specify the
location of the component in the package structure.

You also set the `source-path` to the current directory or a directory from
which the component directory can be determined.

You can also add the framework.swc and framework_rb.swc files to the
`library-path` option. This addition is not always required if the compiler can
determine the location of these SWC files on its own. However, if you move the
compiler utility out of the default location relative to the frameworks files,
you must add it to the library path.

The previous command-line example appears in a configuration file as follows:

    <compiler>
    	<source-path>
    		<path-element>.</path-element>
    	</source-path>
    	<output>
    		c:/jrun4/servers/flex/WEB-INF/flex/user_classes/RotationClasses.swc
    	</output>
    </compiler>
    <include-classes>
    	<class>rotationClasses.Rotation</class>
    	<class>rotationClasses.RotationInstance</class>
    </include-classes>

To use components that are not in a package in an application, you must declare
a namespace that includes the directory structure of the components. The
following example declares a namespace for the components compiled in the
previous example:

    <?xml version="1.0"?>
    <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
    	xmlns:s="library://ns.adobe.com/flex/spark"
    	xmlns:mx="library://ns.adobe.com/flex/mx"
    	xmln:local="rotationclasses.*">
    	...
    	<local:Rotation id="Rotate75" angleFrom="0" angleTo="75" duration="100"/>
    	...
    </s:Application>

To use the generic namespace of "\*" rather than a namespace that includes a
component's directory structure, you can include the directory in the
`source-path` as the following command-line example shows:

    compc -source-path . c:/flexdeploy/comps/rotationClasses
    	-output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/RotationComps.swc
    	-include-classes Rotation RotationInstance

Then, you can specify the namespace in your application as:

    <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
    	xmlns:s="library://ns.adobe.com/flex/spark"
    	xmlns:mx="library://ns.adobe.com/flex/mx"
    	xmln:local="*">

You are not required to use the directory name in the `include-classes` option
if you add the directory to the source path.

These options appear in a configuration file, as the following example shows:

    <compiler>
    	<source-path>
    		<path-element>.</path-element>
    		<path-element>c:/flexdeploy/comps/rotationClasses</path-element>
    	</source-path>
    	<output>c:/jrun4/servers/flex/WEB-INF/flex/user_classes/RotationComps.swc</output>
    </compiler>
    <include-classes>
    	<class>Rotation</class>
    	<class>RotationInstance</class>
    <include-classes>

This example assumes that the components are not in a named package. For
information about compiling packaged components, see
[Compiling components in packages](./compiling-components-in-packages.md).
