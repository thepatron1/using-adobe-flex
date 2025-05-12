# Setting the file encoding

You use the `actionscript-file-encoding` option to set the file encoding so that
the application compiler correctly interprets ActionScript files. This tag does
not affect MXML files because they are XML files that contain an encoding
specification in the `xml` tag.

You use the `actionscript-file-encoding` option when your ActionScript files do
not contain a Byte Order Mark (BOM), and the files use an encoding that is
different from the default encoding of your computer. If your ActionScript files
contain a BOM, the compiler uses the information in the BOM to determine the
file encoding.

For example, if your ActionScript files use Shift_JIS encoding, have no BOM, and
your computer uses ISO-8859-1 as the default encoding, you use the
`actionscript-file-encoding` option, as the following example shows:

    actionscript-file-encoding=Shift_JIS
