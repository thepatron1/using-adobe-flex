# Compiling components in packages

Some components are created inside packages or directory structures so that they
can be logically grouped and separated from application code. As a result,
packaged components can have a namespace declaration that includes the package
name or a unique namespace identifier that references their location within a
package.

You compile packaged components similarly to how you compile components that are
not in packages. The only difference is that you must use the package name in
the namespace declaration, regardless of how you compiled the SWC file, and that
package name uses dot-notation instead of slashes. You must be sure to specify
the location of the classes in the `source-path`.

In the following command-line example, the MyButton component is in the
mypackage package:

    compc -source-path . c:/flexdeploy/comps/mypackage/
        -output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MyButtonComp.swc
        -include-classes mypackage.MyButton

These options appear in a configuration file, as the following example shows:

    <compiler>
        <source-path>
            <path-element>.</path-element>
            <path-element>c:/flexdeploy/comps/mypackage/</path-element>
        </source-path>
        <output>
            c:/jrun4/servers/flex/WEB-INF/flex/user_classes/MyButtonComp.swc
        </output>
    </compiler>
    <include-classes>
        <class>mypackage.MyButton</class>
    <include-classes>

To access the MyButton class in your application, you must declare a namespace
that includes its package; for example:

    <s:Application
        xmlns:fx="http://ns.adobe.com/mxml/2009"
        xmlns:s="library://ns.adobe.com/flex/spark"
        xmlns:mx="library://ns.adobe.com/flex/mx"
        xmlns:mine="mypackage.*">

You can use the compc compiler to compile components from multiple packages into
a single SWC file. In the following command-line example, the MyButton control
is in the mypackage package, and the CustomComboBox control is in the acme
package:

    compc -source-path .
        -output c:/jrun4/servers/flex/WEB-INF/flex/user_classes/CustomComps.swc
        -include-classes mypackage.MyButton
        acme.CustomComboBox

You then define each package as a separate namespace in your MXML application:

    <?xml version="1.0"?>
    <s:Application <s:Application
        xmlns:fx="http://ns.adobe.com/mxml/2009"
        xmlns:s="library://ns.adobe.com/flex/spark"
        xmlns:mx="library://ns.adobe.com/flex/mx"
        xmlns:mine="mypackage.*"
        xmlns:acme="acme.*">
        <mine:MyButton/>
        <acme:CustomComboBox/>
    </s:Application>
