# Using SWC files

Often, you use SWC files when compiling MXML files. SWC files can provide
themes, components, or other helper files. You typically specify SWC files used
by the application by using the `library-path` option.

The following example compiles the RotationApplication.mxml file into the
RotationApplication.swf file:

    mxmlc -library-path+=c:/mylibraries/MyButtonSwc.swc c:/myfiles/comptest/testRotation.mxml

In a configuration file, this appears as follows:

    <compiler>
        <library-path>
            <path-element>libs</path-element>
            <path-element>libs/player</path-element>
            <path-element>libs/player/{targetPlayerMajorVersion}.{targetPlayerMinorVersion}</path-element>
            <path-element>locale/{locale}</path-element>
            <path-element>c:/mylibraries/MyButtonSwc.swc</path-element>
        </library-path>
    </compiler>
