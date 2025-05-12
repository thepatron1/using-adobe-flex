# Compiling components using namespaces

When you have many components in one or more packages that you want to add to a
SWC file and want to reference from an MXML file through a custom namespace, you
can list them in a manifest file, then reference that manifest file on the
command line. Also, you can specify a namespace for that component or define
multiple manifest files and, therefore, specify multiple namespaces to compile
into a single SWC file.

When you use manifest files to define the components in your SWC file, you
specify the namespace that the components use in your applications. You can
compile all the components from one or more packages into a single SWC file. If
you have more than one package, you can set it up so that all packages use a
single namespace or so that each package has an individual namespace.

More Help topics

[Components in a single namespace](./components-in-a-single-namespace.md)

[Components in multiple namespaces](./components-in-multiple-namespaces.md)
