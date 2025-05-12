# Basic example of using mxmlc

The most basic example is one in which the MXML file has no external
dependencies (such as components in a SWC file or ActionScript classes) and no
special options. In this case, you invoke the mxmlc compiler and point it to
your MXML file as the following example shows:

    mxmlc c:/myfiles/app.mxml

The default option is the target file to compile into a SWF file, and it is
required to have a value. If you use a space-separated list as part of the
options, you can terminate the list with a double hyphen before adding the
target file; for example:

    mxmlc -option arg1 arg2 arg3 -- target_file.mxml
