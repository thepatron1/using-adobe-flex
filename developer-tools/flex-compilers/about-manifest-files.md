# About manifest files

Manifest files map a component namespace to class names. They define the package
names that the components used before being compiled into a SWC file. They are
not required when compiling SWC files, but they can help keep your source files
organized.

Manifest files use the following syntax:

    <?xml version="1.0"?>
    <componentPackage>
        <component id="component_name" class="component_class"/>
        [...]
    </componentPackage>

For example:

    <?xml version="1.0"?>
    <componentPackage>
        <component id="MyButton" class="package1.MyButton"/>
        <component id="MyOtherButton" class="package2.MyOtherButton"/>
    </componentPackage>

In a manifest file, the `id` property of each `<component>` tag must be unique.
It is the name you use for the tag in your applications. For example, you define
the `id` as `MyButton` in the manifest file:

    <component id="MyButton" class="asbutton.MyButton"/>

In your application, you use `MyButton` as the tag name:

    <local:MyButton label="Click Me"/>

The `id` property in the manifest file entry is optional. If you omit it, you
can use the class name as the tag. This is useful if you have two classes with
the same name in different packages. In this case, you use the manifest to
define the tags, as the following example shows:

    <?xml version="1.0"?>
    <componentPackage>
        <component id="BoringButton" class="boring.MyButton"/>
        <component id="GreatButton" class="great.MyButton"/>
    </componentPackage>

Some SWC files consist of multiple components from different packages, so compc
includes a manifest file with your SWC file in those cases to prevent compiler
errors.

When compiling the SWC file, you specify the manifest file by using the
`namespace` and the `include-namespaces` options. You define the namespace and
its contents with the namespace option:

    -namespace http://mynamespace mymanifest.xml

Then you identify that namespace's contents for inclusion in the SWC file:

    -include-namespaces http://mynamespace
