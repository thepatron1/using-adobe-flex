# Components in a single namespace

In the manifest file, you define which components are in a namespace. The
following sample manifest file defines two components to be included in the
namespace:

    <?xml version="1.0"?>
    <!-- SimpleManifest.xml -->
    <componentPackage>
    	<component id="MyButton" class="MyButton"/>
    	<component id="MyOtherButton" class="MyOtherButton"/>
    </componentPackage>

The manifest file can contain references to any number of components in a
namespace. The `class` option is the full class name (including package) of the
class. The `id` property is optional, but you can use it to define the MXML tag
interface that you use in your applications. If the compiler cannot find one or
more files listed in the manifest, it throws an error. For more information on
using manifest files, see [About manifest files](../../about-manifest-files.md).

On the command line, you define the namespace with the `namespace` option; for
example:

    -namespace http://mynamespace SimpleManifest.xml

Next, you target the defined namespace for inclusion in the SWC file with the
`include-namespaces` option; for example:

    -include-namespaces http://mynamespace

The `namespace` option matches a namespace (such as
`http://ns.adobe.com/mxml/2009`) with a manifest file. The `include-namespaces`
option instructs compc to include all the components listed in that namespace's
manifest file in the SWC file.

After you define the manifest file, you can compile the SWC file. The following
command-line example compiles the components into the `http://mynamespace`
namespace:

    compc -source-path .
    	-output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MyButtons.swc
    	-namespace http://mynamespace SimpleManifest.xml
    	-include-namespaces http://mynamespace

In a configuration file, these options appear as the following example shows:

    <compiler>
    	<source-path>
    		<path-element>.</path-element>
    	</source-path>
    	<output>c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MyButtons.swc</output>
    	<namespaces>
    		<namespace>
    			<uri>http://mynamespace</uri>
    			<manifest>SimpleManifest.xml</manifest>
    		</namespace>
    	</namespaces>
    </compiler>
    <include-namespaces>
    	<uri>http://mynamespace</uri>
    <include-namespaces>

In your application, you can access the components by defining the new namespace
in the `<s:Application>` tag, as the following example shows:

    <?xml version="1.0"?>
    <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
    	xmlns:s="library://ns.adobe.com/flex/spark"
    	xmlns:mx="library://ns.adobe.com/flex/mx"
    	xmlns:a="http://mynamespace">
    	<a:MyButton/>
    	<a:MyOtherButton/>
    </s:Application>
