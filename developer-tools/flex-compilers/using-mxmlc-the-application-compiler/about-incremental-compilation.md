# About incremental compilation

You can use incremental compilation to decrease the time it takes to compile an
application or component library with the application compilers. When
incremental compilation is enabled, the compiler inspects changes to the
bytecode between revisions and only recompiles the section of bytecode that has
changed. These sections of bytecode are also referred to as _compilation units_.

You enable incremental compilation by setting the `incremental` option to
`true`, as the following example shows:

    mxmlc -incremental=true MyApp.mxml

Incremental compilation means that the compiler inspects your code, determines
which parts of the application are affected by your changes, and only recompiles
the newer classes and assets. The Flex compilers generate many compilation units
that do not change between compilation cycles. It is possible that when you
change one part of your application, the change might not have any effect on the
bytecode of another.

As part of the incremental compilation process, the compiler generates a cache
file that lists the compilation units of your application and information on
your application's structure. This file is located in the same directory as the
file that you are compiling. For example, if my application is called
MyApp.mxml, the cache file is called MyApp.mxml.cache. This file helps the
compiler determine which parts of your application must be recompiled. One way
to force a complete recompile is to delete the cache file from the directory.

Incremental compilation can help reduce compile time on small applications, but
you achieve the biggest gains on larger applications.

The default value of the `incremental` compiler option is `true` for the Flash
Builder application compiler. For the mxmlc command-line compiler, the default
is `false`.
