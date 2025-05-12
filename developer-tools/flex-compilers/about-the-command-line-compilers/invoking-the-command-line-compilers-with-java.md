# Invoking the command-line compilers with Java

Flex provides a simple interface to the command-line compilers. For UNIX users,
there is a shell script. For Windows users, there is an executable file. These
files are located in the bin directory. You can also invoke the compilers using
Java. This lets you integrate the compilers into Java-based projects (such as
Ant) or other utilities.

The shell scripts and executable files for the command-line compilers wrap calls
to the mxmlc.jar and compc.jar JAR files. To invoke the compilers from Java, you
call the JAR files directly. For Flex SDK, the JAR files are located in the
_flex_install_dir_/lib directory. For Flash Builder, they are located in the
_flash_builder_install_dir_/sdks/_sdk_version_/lib.

To invoke a command in a JAR file, use the `java` command from the command line
and specify the JAR file you want to execute with the `jar` option. You must
also specify the value of the `+flexlib` option. This advanced option lets you
set the root directory that is used by the compiler to locate the
flex-config.xml file, among other files. You typically point it to your
frameworks directory. From there, the compiler can detect the location of other
configuration files.

The following example compiles MyApp.mxml into a SWF file using the JAR file to
invoke the mxmlc compiler:

    java -jar ../lib/mxmlc.jar +flexlib c:/flex_4_sdk/frameworks c:/flex/MyApp.mxml

You pass all other options as you would when you open the command-line
compilers. The following example sets the locale and source path when compiling
MyApp:

    java -jar ../lib/mxmlc.jar +flexlib c:/flex_4_sdk/frameworks -locale en_US -source-path locale/{locale} c:/flex/MyApp.mxml
