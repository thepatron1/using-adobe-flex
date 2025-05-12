# Components in multiple namespaces

You can use the compc compiler to compile components that use multiple
namespaces into a SWC file. Each namespace must have its own manifest file.

The following command-line example compiles components defined in the
AcmeManifest.xml and SimpleManifest.xml manifest files:

    compc -source-path .
        -output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MyButtons.swc
        -namespace http://acme2009 AcmeManifest.xml
        -namespace http://mynamespace SimpleManifest.xml
        -include-namespaces http://acme2009 http://mynamespace

In this case, all components in both the `http://mynamespace` and
`http://acme2009` namespaces are targeted and included in the output SWC file.

In a configuration file, these options appear as the following example shows:

    <compiler>
        <source-path>
            <path-element>.</path-element>
        </source-path>
        <output>c:/jrun4/servers/flex/flex/WEB-INF/flex/user_classes/        MyButtons.swc</output>
        <namespaces>
            <namespace>
                <uri>http://acme2009</uri>
                <manifest>AcmeManifest.xml</manifest>
            </namespace>
            <namespace>
                <uri>http://mynamespace</uri>
                <manifest>SimpleManifest.xml</manifest>
            </namespace>
        </namespaces>
    </compiler>
    <include-namespaces>
        <uri>http://acme2009</uri>
        <uri>http://mynamespace</uri>
    <include-namespaces>

In your MXML application, you define both namespaces separately:

    <?xml version="1.0"?>
    <s:Application xmlns:fx="http://ns.adobe.com/mxml/2009"
        xmlns:s="library://ns.adobe.com/flex/spark"
        xmlns:mx="library://ns.adobe.com/flex/mx"
        xmlns:simple="http://mynamespace"
        xmlns:acme="http://acme2009">
        <simple:SimpleComponent/>
        <acme:AcmeComponent/>
    </s:Application>

You are not required to include all namespaces that you define as target
namespaces. You can define multiple namespaces, but use only one target
namespace. You might do this if some components use other components that are
not directly exposed as MXML tags. You cannot then directly access the
components in the unused namespace, however.

The following command line example defines two namespaces, `http://acme2009` and
`http://mynamespace`, but only includes one as a namespace target:

    compc -source-path .
        -output c:/jrun4/servers/flex/flex/WEB-INF/flex/user_classes/MyButtons.swc
        -namespace http://acme2009 AcmeManifest.xml
        -namespace http://mynamespace SimpleManifest.xml
        -include-namespaces http://mynamespace
