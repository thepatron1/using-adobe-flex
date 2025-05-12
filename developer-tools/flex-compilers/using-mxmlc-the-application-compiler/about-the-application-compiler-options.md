# About the application compiler options

The following table describes the application compiler options. You invoke the
application compiler with the mxmlc command-line utility or when building a
project in Flash Builder.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div>
<pre><code>accessible=true|false</code></pre>
</div></td>
<td><p>Enables accessibility features when compiling the application or
SWC file. The default value is <samp>false</samp>.</p>
<p>For more information on using the Flex accessibility features, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f60.html">Accessible
applications</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>actionscript-file-encoding string</code></pre>
</div></td>
<td><p>Sets the file encoding for ActionScript files.</p>
<p>For more information, see <a href="./setting-the-file-encoding.md">Setting the file
encoding</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>advanced</code></pre>
</div></td>
<td><p>Lists advanced help options when used with the help option, as
the following example shows:</p>
<div>
<pre><code>mxmlc -help advanced</code></pre>
</div>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>allow-source-path-overlap=true|false</code></pre>
</div></td>
<td><p>Checks if a <samp>source-path</samp> entry is a subdirectory of
another <samp>source-path</samp> entry. It helps make the package names
of MXML components unambiguous.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>as3=true|false</code></pre>
</div></td>
<td><p>Use the ActionScript 3.0 class-based object model for greater
performance and better error reporting. In the class-based object model,
most built-in functions are implemented as fixed methods of classes.</p>
<p>The default value is <samp>true</samp>. If you set this value to
<samp>false</samp>, you must set the <samp>es</samp> option to
<samp>true</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>benchmark=true|false</code></pre>
</div></td>
<td><p>Prints detailed compile times to the standard output. The default
value is <samp>true</samp>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>compress=true|false</samp></p></td>
<td><p>Enables or disables SWF file compression.</p>
<p>The default value is <samp>true</samp> when debugging is disabled (so
that release SWF files are compressed) and <samp>false</samp> when
debugging is enabled (so that debug SWF files are not
compressed).</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>context-root context-path</code></pre>
</div></td>
<td><p>Sets the value of the <samp>{context.root}</samp> token, which is
often used in channel definitions in the flex-services.xml file and
other settings in the flex-config.xml file. The default value is
null.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>contributor name</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>creator name</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>date text</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>debug=true|false</code></pre>
</div></td>
<td><p>Generates a debug SWF file. This file includes line numbers and
filenames of all the source files. When a run-time error occurs, the
stacktrace shows these line numbers and filenames. This information is
used by the command-line debugger and the Flex Builder debugger.
Enabling the <samp>debug</samp> option generates larger SWF files and
also disables compilation optimization.</p>
<p>For the mxmlc compiler, the default value is <samp>false</samp>. For
the compc compiler, the default value is <samp>true</samp>.</p>
<p>For Flash Builder, the default value is <samp>true</samp>. If you
export an application by using the Export Release Build feature, the
Flash Builder compiler excludes the debugging information, which is the
equivalent of setting the value of this option to
<samp>false</samp>.</p>
<p>When generating SWC files, if <samp>debug</samp> is set to
<samp>true</samp>, then the library.swf file inside the SWC file
contains debug information. If you are generating a SWC file for
distribution, set this value to <samp>false</samp>.</p>
<p>For information about the command-line debugger, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7ffb.html">Command-line
debugger</a>.</p>
<p>If you set this option to <samp>true</samp>, Flex also sets the
<samp>verbose-stacktraces</samp> option to <samp>true</samp></p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>debug-password string</code></pre>
</div></td>
<td><p>Lets you engage in remote debugging sessions with the Flash
IDE.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>default-frame-rate int</code></pre>
</div></td>
<td><p>Sets the application's frame rate. The default value is 24.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>default-script-limits max-recursion-depth max-execution-time</code></pre>
</div></td>
<td><p>Defines the application's script execution limits.</p>
<p>The <samp>max-recursion-depth</samp> value specifies the maximum
depth of Adobe Flash Player call stack before Flash Player stops. This
is essentially the stack overflow limit. The default value is 1000.</p>
<p>The <samp>max-execution-time</samp> value specifies the maximum
duration, in seconds, that an ActionScript event handler can execute
before Flash Player assumes that it is hung, and aborts it. The default
value is 60 seconds. You cannot set this value above 60 seconds.</p>
<p>You can override these settings in the application.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>default-size width height</code></pre>
</div></td>
<td><p>Defines the default application size, in pixels.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>defaults-css-files filename [, ...]</code></pre>
</div></td>
<td><p>Inserts CSS files into the output the same way that a per-SWC
defaults.css file works, but without having to re-archive the SWC file
to test each change.</p>
<p>CSS files included in the output with this option have a higher
precedence than default CSS files in existing SWCs. For example, a CSS
file included with this option overrides definitions in framework.swc's
defaults.css file, but it has the same overall precedence as other
included CSS files inside the SWC file.</p>
<p>This option does not actually insert the CSS file into the SWC file;
it simulates it. When you finish developing the CSS file, you should
rebuild the SWC file with the new integrated CSS file.</p>
<p>This option takes one or more files. The precedence for multiple CSS
files included with this option is from first to last.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>defaults-css-url string</code></pre>
</div></td>
<td><p>Defines the location of the default style sheet. Setting this
option overrides the implicit use of the defaults.css style sheet in the
framework.swc file.</p>
<p>For more information on the defaults.css file, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fee.html">Styles and
themes</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>define=NAMESPACE::variable,value</code></pre>
</div></td>
<td><p>Defines a global constant. The value is evaluated at compile time
and exists as a constant within the application. A common use of inline
constants is to set values that are used to include or exclude blocks of
code, such as debugging or instrumentation code. This is known as
conditional compilation.</p>
<p>The following example defines the constant <samp>debugging</samp> in
the <samp>CONFIG</samp> namespace:</p>
<div>
<pre><code>-define=CONFIG::debugging,true</code></pre>
</div>
<p>In ActionScript, you can use this value to conditionalize statements;
for example:</p>
<div>
<pre><code>CONFIG::debugging {// Execute debugging code here.}</code></pre>
</div>
<p>To set multiple conditionals on the command-line, use the
<samp>define</samp> option more than once.</p>
<p>For more information, see <a href="./using-conditional-compilation.md">Using conditional
compilation</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>description text</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>dump-config filename</code></pre>
</div></td>
<td><p>Outputs the compiler options in the flex-config.xml file to the
target path; for example:</p>
<div>
<pre><code>mxmlc -dump-config myapp-config.xml</code></pre>
</div>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>es=true|false</code></pre>
</div></td>
<td><p>Instructs the compiler to use the ECMAScript edition 3
prototype-based object model to allow dynamic overriding of prototype
properties. In the prototype-based object model, built-in functions are
implemented as dynamic properties of prototype objects.</p>
<p>The default value is <samp>false</samp>.</p>
<p>Using the ECMAScript edition 3 prototype-based object model lets you
use untyped properties and functions in your application code. As a
result, if you set the value of the <samp>es</samp> compiler option to
<samp>true</samp>, you must set the <samp>strict</samp> compiler option
to <samp>false</samp>. Otherwise, the compiler will throw errors.</p>
<p>If you set this option to <samp>true</samp>, you must also set the
value of the <samp>as3</samp> compiler option to <samp>false</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>externs class_name [...]</code></pre>
</div></td>
<td><p>Sets a list of classes to exclude from linking when compiling a
SWF file.</p>
<p>This option provides compile-time link checking for external
references that are dynamically linked.</p>
<p>For more information about dynamic linking, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f1e.html">About
linking</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>external-library-path path-element [...]</code></pre>
</div></td>
<td><p>Specifies a list of SWC files or directories to exclude from
linking when compiling a SWF file. This option provides compile-time
link checking for external components that are dynamically linked.</p>
<p>By default, the libs/player/playerglobal.swc file is linked as an
external library. This library is built into Flash Player.</p>
<p>For more information about dynamic linking, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f1e.html">About
linking</a>.</p>
<p>You can use the += operator to append the new SWC file to the list of
external libraries.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>fonts.advanced-anti-aliasing=true|false</code></pre>
</div></td>
<td><p>Sets the default value that determines whether embedded fonts use
advanced anti-aliasing information when rendering the font.</p>
<p>Setting the value of the <samp>advanced-anti-aliasing</samp> property
in a style sheet overrides this value.</p>
<p>The default value is <samp>false</samp>.</p>
<p>For more information about using advanced anti-aliasing, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f9e.html">Fonts</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>fonts.languages.language-range lang range</code></pre>
</div></td>
<td><p>Specifies the range of Unicode settings for that language. For
more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f9e.html">Fonts</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>fonts.local-fonts-snapshot path_to_file</code></pre>
</div></td>
<td><p>Sets the location of the local font snapshot file. The file
contains system font data.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>fonts.managers manager-class [...]</code></pre>
</div></td>
<td><p>Defines the font manager. The default is
flash.fonts.JREFontManager. You can also use the
flash.fonts.BatikFontManager. For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f9e.html">Fonts</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>fonts.max-cached-fonts string</code></pre>
</div></td>
<td><p>Sets the maximum number of fonts to keep in the server
cache.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>fonts.max-glyphs-per-face string</code></pre>
</div></td>
<td><p>Sets the maximum number of character glyph-outlines to keep in
the server cache for each font face.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>frames.frame=label,class_name[,...]</code></pre>
</div></td>
<td><div>
Specifies a SWF file frame label with a sequence of class names that are
linked onto the frame; for example:
<pre><code>-frame=MyLabel,Class1,Class2</code></pre>
</div>
<p>This option lets you add asset factories that stream in after the
application that then publish their interfaces with the ModuleManager
class. The advantage to doing this is that the application starts faster
than it would have if the assets had been included in the code, but does
not require moving the assets to an external SWF file.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>generate-frame-loader=true|false</code></pre>
</div></td>
<td><p>Toggles the generation of an IFlexBootstrap-derived loader
class.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>headless-server=true|false</code></pre>
</div></td>
<td><p>Enables the headless implementation of the Flex compiler. This
sets the following:</p>
<div>
<pre><code>System.setProperty(&quot;java.awt.headless&quot;, &quot;true&quot;)</code></pre>
</div>
<p>The headless setting (java.awt.headless=true) is required to use
fonts and SVG on UNIX systems without X Windows.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>help [-list [advanced]]</code></pre>
</div></td>
<td><div>
Prints usage information to the standard output. For example:
<pre><code>help -list advanced</code></pre>
</div>
<p>For more information, see <a href="../about-the-command-line-compilers/command-line-syntax.md">Command-line
syntax</a>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>include-inheritance-dependencies-only=false|true</samp></p></td>
<td><p>Include only classes that are inheritance dependencies of classes
that are included with the <samp>include-classes</samp> compiler
option.</p>
<p>The default value is <samp>false</samp>.</p>
<div>
This is an advanced option. You might use this compiler option if you
are creating a custom RSL and want to externalize as many classes as
possible. For example:
<pre><code>compc -include-classes mx.collections.ListCollectionView 
-include-inheritance-dependencies-only=true 
-source-path . -output lcv2 -directory</code></pre>
</div></td>
</tr>
<tr class="even">
<td><div>
<pre><code>include-libraries library [...]</code></pre>
</div></td>
<td><p>Links all classes inside a SWC file to the resulting application
SWF file, regardless of whether or not they are used.</p>
<p>Contrast this option with the <samp>library-path</samp> option that
includes only those classes that are referenced at compile time.</p>
<p>To link one or more classes whether or not they are used and not an
entire SWC file, use the <samp>includes</samp> option.</p>
<p>This option is commonly used to specify resource bundles.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>include-resource-bundles bundle [...]</code></pre>
</div></td>
<td><p>Specifies the resource bundles to link into a resource module.
All resource bundles specified with this option must be in the
compiler's source path. You specify this using the
<samp>source-path</samp> compiler option.</p>
<p>For more information on using resource bundles, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fcf.html">Resource
Bundles</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>includes class [...]</code></pre>
</div></td>
<td><p>Links one or more classes to the resulting application SWF file,
whether or not those classes are required at compile time.</p>
<p>To link an entire SWC file rather than individual classes, use the
<samp>include-libraries</samp> option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>incremental=true|false</code></pre>
</div></td>
<td><p>Enables incremental compilation. For more information, see <a href="./about-incremental-compilation.md">About incremental compilation</a>.</p>
<p>This option is <samp>true</samp> by default for the Flash Builder
application compiler. For the command-line compiler, the default is
<samp>false</samp>.</p></td>
</tr>
<tr class="even">
<td><p><samp>isolate-styles=true|false</samp></p></td>
<td><p>Enables per-module styling.</p>
<p>The default value is <samp>true</samp>.</p>
<p>This is an advanced option. You typically only use this option if you
want to set styles in a module that is loaded into your main
application. For more information about modules, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f22.html">Modular
applications</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>keep-as3-metadata=class_name [...]</code></pre>
</div></td>
<td><p>Specifies custom metadata that you want to keep. By default, the
compiler keeps the following metadata:</p>
<div>
<ul class="incremental">
<li><p>Bindable</p></li>
<li><p>Managed</p></li>
<li><p>ChangeEvent</p></li>
<li><p>NonCommittingChangeEvent</p></li>
<li><p>Transient</p></li>
</ul>
</div>
<p>If you want to preserve the default metadata, you should use the +=
operator to append your custom metadata, rather than the = operator
which replaces the default metadata.</p>
<p>This is an advanced option. For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7ab2.html">About metadata
tags</a>.</p></td>
</tr>
<tr class="even">
<td><p><samp>keep-all-type-selectors=true|false</samp></p></td>
<td><p>Instructs the compiler to keep a style sheet's type selector in a
SWF file, even if that type (the class) is not used in the application.
This is useful when you have a modular application that loads other
applications. For example, the loading SWF file might define a type
selector for a type used in the loaded (or, target) SWF file. If you set
this option to <samp>true</samp> when compiling the loading SWF file,
then the target SWF file will have access to that type selector when it
is loaded. If you set this option to <samp>false</samp>, the compiler
will not include that type selector in the loading SWF file at compile
time. As a result, the styles will not be available to the target SWF
file.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>keep-generated-actionscript=true|false</code></pre>
</div></td>
<td><p>Determines whether to keep the generated ActionScript class
files.</p>
<p>The generated class files include stubs and classes that are
generated by the compiler and used to build the SWF file.</p>
<p>When using the application compiler, the default location of the
files is the /generated subdirectory, which is directly below the target
MXML file. If the /generated directory does not exist, the compiler
creates one. When using the compc component compiler, the default
location of the /generated directory is relative to the output of the
SWC file. When using Flash Builder, the default location of the
generated files is the /bin/generated directory.</p>
<p>The default names of the primary generated class files are
filename-generated.as and filename-interface.as.</p>
<p>The default value is <samp>false</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>language code</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>library-path path-element [...]</code></pre>
</div></td>
<td><p>Links SWC files to the resulting application SWF file. The
compiler only links in those classes for the SWC file that are required.
You can specify a directory or individual SWC files.</p>
<p>The default value of the <samp>library-path</samp> option includes
all SWC files in the libs and libs/player directories, plus the current
locale directory. These are required.</p>
<p>To point to individual classes or packages rather than entire SWC
files, use the <samp>source-path</samp> option.</p>
<p>If you set the value of the <samp>library-path</samp> as an option of
the command-line compiler, you must also explicitly add the
framework.swc and locale SWC files. Your new entry is not appended to
the <samp>library-path</samp> but replaces it, unless you use the +=
operator.</p>
<p>On the command line, you use the += operator to append the new
argument to the list of existing SWC files.</p>
<p>In a configuration file, you can set the <samp>append</samp>
attribute of the <samp>library-path</samp> tag to <samp>true</samp> to
indicate that the values should be appended to the library path rather
than replace existing default entries.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>license product_name  license_key</code></pre>
</div></td>
<td><p>Defines the license key to use when compiling.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>link-report filename</code></pre>
</div></td>
<td><p>Prints linking information to the specified output file. This
file is an XML file that contains <samp>&lt;def&gt;</samp>,
<samp>&lt;pre&gt;</samp>, and <samp>&lt;ext&gt;</samp> symbols showing
linker dependencies in the final SWF file.</p>
<p>The output of this command can be used as input to the
<samp>load-externs</samp> option.</p>
<p>For more information on the report, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7adc.html">Examining linker
dependencies</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>load-config filename</code></pre>
</div></td>
<td><p>Specifies the location of the configuration file that defines
compiler options.</p>
<p>If you specify a configuration file, you can override individual
options by setting them on the command line.</p>
<p>All relative paths in the configuration file are relative to the
location of the configuration file itself.</p>
<p>Use the <samp>+=</samp> operator to chain this configuration file to
other configuration files.</p>
<p>For more information on using configuration files to provide options
to the command-line compilers, see <a href="../about-configuration-files/index.md">About
configuration files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>load-externs filename [...]</code></pre>
</div></td>
<td><p>Specifies the location of an XML file that contains
<samp>&lt;def&gt;</samp>, <samp>&lt;pre&gt;</samp>, and
<samp>&lt;ext&gt;</samp> symbols to omit from linking when compiling a
SWF file. The XML file uses the same syntax as the one produced by the
<samp>link-report</samp> option. For more information on the report, see
<a href="WS2db454920e96a9e51e63e3d11c0bf69084-7adc.html">Examining
linker dependencies</a>.</p>
<p>This option provides compile-time link checking for external
components that are dynamically linked.</p>
<p>For more information about dynamic linking, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f1e.html">About
linking</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>locale locale[,...]</code></pre>
</div></td>
<td><p>Specifies one or more locales to be compiled into the SWF file.
If you do not specify a locale, then the compiler uses the default
locale from the flex-config.xml file. The default value is en_US. You
can append additional locales to the default locale by using the +=
operator.</p>
<p>If you remove the default locale from the flex-config.xml file, and
do not specify one on the command line, then the compiler will use the
machine's locale.</p>
<p>For more information, see <a
href="WS19f279b149e7481c-1c03f02c12bd00c4763-8000.html">Localization</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>localized-description text lang</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>localized-title text lang</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>mxml.compatibility-version=version</code></pre>
</div></td>
<td><p>Specifies the version of the Flex compiler that the output should
be compatible with. This option affects some behavior such as the layout
rules, padding and gaps, skins, and other style settings. In addition,
it affects the rules for parsing properties files.</p>
<p>The following example instructs the application to compile with the
Flex 3 rules for these behaviors:</p>
<div>
<pre><code>-compatibility-version=3.0.0</code></pre>
</div>
<p>Possible values for this compiler option are defined as constants in
the <a
href="https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/core/FlexVersion.html">FlexVersion</a>
class.</p>
<p>If you set this value to 3.0.0, you must also use a theme in your
application that is compatible with version 3 of the SDK.</p>
<p>For more information on using this option, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7ede.html">Backward
compatibility</a>.</p></td>
</tr>
<tr class="even">
<td><p><samp>mxml.minimum-supported-version=</samp><em><samp>version_number</samp></em></p></td>
<td><p>Specifies the minimum version of the SDK that the application
uses. This is typically used when generating SWC files.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><p><samp>mxml.qualified-type-selectors=true|false</samp></p></td>
<td><p>Determines whether you want the compiler to ensure that type
selectors have a qualified namespace in the CSS files.</p>
<p>This is an advanced option. The default value is
<samp>true</samp>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>namespaces.namespace uri manifest</code></pre>
</div></td>
<td><p>Specifies a namespace for the MXML file. You must include a URI
and the location of the manifest file that defines the contents of this
namespace. This path is relative to the MXML file.</p>
<p>For more information about manifest files, see <a href="../about-manifest-files.md">About manifest
files</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>optimize=true|false</code></pre>
</div></td>
<td><p>Enables the ActionScript optimizer. This optimizer reduces file
size and increases performance by optimizing the SWF file's
bytecode.</p>
<p>The default value is <samp>true</samp>.</p></td>
</tr>
<tr class="even">
<td><p><samp>omit-trace-statements=false|true</samp></p></td>
<td><p>Enables <samp>trace()</samp> statements from being written to the
flashlog.txt file.</p>
<p>The default value is <samp>false</samp>, which means that by default,
<samp>trace()</samp> statements are written to the flashlog.txt
file.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>output filename</code></pre>
</div></td>
<td><p>Specifies the output path and filename for the resulting file. If
you omit this option, the compiler saves the SWF file to the directory
where the target file is located.</p>
<p>The default SWF filename matches the target filename, but with a SWF
file extension.</p>
<p>If you use a relative path to define the filename, it is always
relative to the current working directory, not the target MXML
application root.</p>
<p>The compiler creates extra directories based on the specified
filename if those directories are not present.</p>
<p>When using this option with the component compiler, the output is a
SWC file rather than a SWF file, unless you set the
<samp>directory</samp> option to <samp>true</samp>. In that case, the
output is a directory with the contents of the SWC file. The name of the
directory is that value of the <samp>ouput</samp> option.</p></td>
</tr>
<tr class="even">
<td><p><samp>preloader </samp><em><samp>class_name</samp></em></p></td>
<td><p>Specify a download progress bar for your application. The value
must be the name of a class that implements the IPreloaderDisplay
interface.</p>
<p>The default value is "mx.preloaders.SparkDownloadProgressBar" when
<samp>compatibility-version</samp> is 4.0.0 or greater. When
<samp>compatibility-version</samp> is less than 4.0.0, the default value
is "mx.preloaders.DownloadProgressBar".</p>
<p>For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7e3c.html">Showing the
download progress of an application</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>publisher name</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>raw-metadata XML_string</code></pre>
</div></td>
<td><p>Defines the metadata for the resulting SWF file. The value of
this option overrides any metadata-related compiler options such as
<samp>contributor</samp>, <samp>creator</samp>, <samp>date</samp>, and
<samp>description</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><p><samp>remove-unused-rsls=true|false</samp></p></td>
<td><p>Instructs the compiler to only include RSLs that are used by the
application. The default value is <samp>true</samp>.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>resource-bundle-list filename</code></pre>
</div></td>
<td><p>Prints a list of resource bundles that are used by the current
application to a file named with the <em><samp>filename</samp></em>
argument. You then use this list as input that you specify with the
<samp>include-resource-bundles</samp> option to create a resource
module.</p>
<p>For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fcf.html">Resource
Bundles</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>runtime-shared-libraries rsl-url [...]</code></pre>
</div></td>
<td><p>Specifies a list of runtime shared libraries (RSLs) to use for
this application. RSLs are dynamically-linked at run time. The compiler
externalizes the contents of the application that you are compiling that
overlap with the RSL.</p>
<p>You specify the location of the SWF file relative to the deployment
location of the application. For example, if you store a file named
library.swf file in the <em>web_root</em>/libraries directory on the web
server, and the application in the web root, you specify
libraries/library.swf.</p>
<p>This compiler argument is included for backwards compatibility with
Flex 3 applications. For Flex 4 applications, use the
<samp>runtime-shared-library-path</samp> option.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>runtime-shared-library-path=path-element,rsl-url[,policy-file-url,failover-url,...]</code></pre>
</div></td>
<td><p>Specifies the location of a runtime shared library (RSL). The
compiler externalizes the contents of the application that you are
compiling that overlap with the RSL.</p>
<p>The <samp>path-element</samp> argument is the location of the SWC
file or open directory to compile against. For example,
c:\flexsdk\frameworks\libs\framework.swc. This is the equivalent of the
using the <samp>external-library-path</samp> option when compiling
against an RSL using the <samp>runtime-shared-libraries</samp>
option.</p>
<p>The <samp>rsl-url</samp> argument is the URL of the RSL that will be
used to load the RSL at runtime. The compiler does not verify the
existence of the SWF file at this location at compile time. It does
store this string in the application, however, and uses it at run time.
As a result, the SWF file must be available at run time but necessarily
not at compile time.</p>
<p>The <samp>policy-file-url</samp> is the location of the
crossdomain.xml file that gives permission to read the RSL from the
server. This might be necessary because the RSL can be on a separate
server as the application. For example,
http://www.example.com/rsls/crossdomain.xml.</p>
<p>The <samp>failover-url</samp> and second <samp>policy-file-url</samp>
arguments specify the location of the secondary RSL and crossdomain.xml
file if the first RSL cannot be loaded. This most commonly happens when
the client Player version does not support cross-domain RSLs. You can
add any number of failover RSLs, but must include a policy file URL for
each one.</p>
<p>Do not include spaces between the comma-separated values. The
following example shows how to use this option:</p>
<div>
<pre><code>mxmlc -o=../lib/app.swf -runtime-shared-library-path=../lib/mylib.swc,../bin/myrsl.swf Main.mxml</code></pre>
</div>
<p>You can specify more than one library file to be used as an RSL. You
do this by adding additional <samp>runtime-shared-library-path</samp>
options.</p>
<p>You can also use the <samp>runtime-shared-libraries</samp> command to
use RSLs with your applications. However, the
<samp>runtime-shared-library-path</samp> option lets you also specify
the location of the policy file and failover RSL.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>runtime-shared-library-settings.application-domain=</samp><em><samp>path-element</samp></em><samp>,</samp><em><samp>application-domain-target</samp></em></p></td>
<td><p>Controls which domain an RSL is loaded into at runtime.</p>
<p>The <samp>path-element</samp> is the path of the SWC library. To
specify an RSL with this option, you must also define it in the
<samp>runtime-shared-library-path</samp> option.</p>
<p>The <samp>application-domain-target</samp> is the domain that the RSL
should be loaded into. Valid values for
<samp>application-domain-target</samp> are <samp>default</samp>,
<samp>current</samp>, <samp>parent</samp>, and <samp>top-level</samp>.
The default value is <samp>default</samp>.</p>
<p>For more information about modules, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f22.html">Modular
applications</a>. For more information about sub-applications, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7d14.html">Developing and
loading sub-applications</a>.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><p><samp>runtime-shared-library-settings.force-rsls=</samp><em><samp>path-element</samp></em></p></td>
<td><p>Forces an RSL to be included, regardless of whether it is used by
the application. This is useful if all the links to a particular class
in an RSL are soft references, or if you anticipate a module or
sub-application to need a class that is not used by the main
application.</p>
<p>The <samp>path-element</samp> is the path of the SWC library. You can
specify more than one <samp>path-element</samp> by using a
comma-delimited list of RSLs. To specify an RSL with this option, you
must also define it in the <samp>runtime-shared-library-path</samp>
option.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>services filename</code></pre>
</div></td>
<td><p>Specifies the location of the services-config.xml file. This file
is used by LiveCycle Data Services ES.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>show-actionscript-warnings=true|false</code></pre>
</div></td>
<td><p>Shows warnings for ActionScript classes.</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>show-binding-warnings=true|false</code></pre>
</div></td>
<td><p>Shows a warning when Flash Player cannot detect changes to a
bound property.</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="even">
<td><p><samp>show-invalid-css-property-warnings=true|false</samp></p></td>
<td><p>Shows a warning when a style property is set in CSS on a
component that does not support that property. The warning can be a
result of the theme not supporting the style property, the component not
declaring it, or the component excluding it.</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings and errors</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>show-shadowed-device-font-warnings=true|false</code></pre>
</div></td>
<td><p>Shows warnings when you try to embed a font with a family name
that is the same as the operating system font name. The compiler
normally warns you that you are shadowing a system font. Set this option
to <samp>false</samp> to disable the warnings.</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>show-unused-type-selector-warnings=true|false</code></pre>
</div></td>
<td><p>Shows warnings when a type selector in a style sheet or
<samp>&lt;fx:Style&gt;</samp> block is not used by any components in the
application.</p>
<p>The default value is <samp>true</samp>.</p>
<p>This warning does not detect whether a condition is met for
descendant selectors.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>size-report=</samp><em><samp>filename</samp></em></p></td>
<td><p>Creates a report that summarizes the size of each type of data
within an application SWF file. Types of data include media files,
fonts, shapes, and ActionScript.</p>
<div>
For example:
<pre><code>mxmlc -size-report=myreport.xml MyApp.mxml</code></pre>
</div>
<p>The file format of the output is XML. While the format has some
similarities to the output of the <samp>link-report</samp> option, the
size report cannot be used as input to the <samp>load-externs</samp>
option.</p>
<p>This option is useful if you are optimizing your application and want
to see how big areas of your application are.</p>
<p>For more information about the size report, see <a
href="WS19f279b149e7481c45454d9412c561d3223-8000.html">Using the size
report</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>source-path path-element [...]</code></pre>
</div></td>
<td><p>Adds directories or files to the source path. The Flex compiler
searches directories in the source path for MXML, AS, or CSS source
files that are used in your applications and includes those that are
required at compile time.</p>
<p>You can use wildcards to include all files and subdirectories of a
directory.</p>
<p>To link an entire library SWC file and not individual classes or
directories, use the <samp>library-path</samp> option.</p>
<p>The source path is also used as the search path for the component
compiler's <samp>include-classes</samp> and
<samp>include-resource-bundles</samp> options.</p>
<p>You can also use the += operator to append the new argument to the
list of existing source path entries.</p>
<p>This option has the following default behavior:</p>
<div>
<ul class="incremental">
<li><p>If <samp>source-path</samp> is empty, the target file's directory
will be added to source-path.</p></li>
<li><p>If <samp>source-path</samp> is not empty and if the target file's
directory is a subdirectory of one of the directories in
<samp>source-path</samp>, <samp>source-path</samp> remains
unchanged.</p></li>
<li><p>If <samp>source-path</samp> is not empty and if the target file's
directory is not a subdirectory of any one of the directories in
<samp>source-path</samp>, the target file's directory is prepended to
<samp>source-path</samp>.</p></li>
</ul>
</div></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>static-link-runtime-shared-libraries=true|false</code></pre>
</div></td>
<td><p>Determines whether to compile against libraries statically or use
RSLs. Set this option to <samp>true</samp> to ignore the RSLs specified
by the <samp>runtime-shared-library-path</samp> option. Set this option
to <samp>false</samp> to use the RSLs.</p>
<p>The default value is <samp>true</samp>.</p>
<p>This option is useful so that you can quickly switch between a
statically and dynamically linked application without having to change
the <samp>runtime-shared-library-path</samp> option, which can be
verbose, or edit the configuration files.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>strict=true|false</code></pre>
</div></td>
<td><p>Prints undefined property and function calls; also performs
compile-time type checking on assignments and options supplied to method
calls.\</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information about viewing warnings and errors, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>swf-version=</samp><em><samp>int</samp></em></p></td>
<td><p>Specifies the SWF file format version of the output SWF file.
Features requiring a later version of the SWF file format are not
compiled into the application. This is different from the Player version
in that it refers to the SWF specification versioning scheme.</p>
<p>For Flex 4.6, the default value of <samp>swf-version</samp> is 14
(and the default Player version is 11.1).</p>
<p>This is an advanced option.</p>
<p>For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7ee0.html">Targeting Flash
Player versions</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>target-player=major_version[.minor_version.revision]</code></pre>
</div></td>
<td><p>Specifies the version of Flash Player that you want to target
with the application. Features requiring a later version of Flash Player
are not compiled into the application.</p>
<p>The <em><samp>player_version</samp></em> parameter has the following
format:</p>
<div>
<pre><code>major_version.minor_version.revision</code></pre>
</div>
<p>The <em><samp>major_version</samp></em> is required while
<em><samp>minor_version</samp></em> and <em><samp>revision</samp></em>
are optional. For Flex 4.0 and 4.1, the minimum value is 10.0.0. If you
do not specify the <em><samp>minor_version</samp></em> or
<em><samp>revision</samp></em>, then the compiler uses zeros. For Flex
4.5, the default value is 10.2.0. For Flex 4.6, the default value is
11.1.</p>
<p>If you do not explicitly set the value of this option, the compiler
uses the default from the flex-config.xml file. The value in
flex-config.xml is the version of Flash Player that shipped with the
SDK.</p>
<p>This option is useful if your application's audience has a specific
Player and cannot upgrade. You can use this option to "downgrade" your
application for that audience.</p>
<p>For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7ee0.html">Targeting Flash
Player versions</a></p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>theme filename [...]</code></pre>
</div></td>
<td><p>Specifies a list of theme files to use with this application.
Theme files can be SWC files with CSS files inside them or CSS
files.</p>
<p>For information on compiling a SWC theme file, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fee.html">Styles and
themes</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>title text</code></pre>
</div></td>
<td><p>Sets metadata in the resulting SWF file. For more information,
see <a href="./adding-metadata-to-swf-files.md">Adding
metadata to SWF files</a>.</p></td>
</tr>
<tr class="odd">
<td><p><samp>tools-locale=</samp><em><samp>locale</samp></em></p></td>
<td><p>Specifies the locale to use when reporting compiler errors and
warnings. Valid values are the language code (such as "ja" or "en") or
the language code plus country code (such as "ja_JP" or "en_US"),
depending on your system's configuration.</p></td>
</tr>
<tr class="even">
<td><p><samp>use-direct-blit=false|true</samp></p></td>
<td><p>Specifies whether hardware acceleration is used to copy graphics
to the screen (if such acceleration is available).</p>
<p>This option only applies to applications running in the standalone
Flash Player. For applications running in a browser, setting
<samp>use-direct-blit</samp> to <samp>true</samp> is equivalent to
setting <samp>wmode</samp> to <samp>"direct"</samp> in the HTML wrapper.
For AIR applications, use the <samp>renderMode</samp> application
descriptor tag.</p>
<p>The default value is <samp>false</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="odd">
<td><p><samp>use-gpu=false|true</samp></p></td>
<td><p>Specifies whether GPU (Graphics Processing Unit) acceleration is
used when drawing graphics (if such acceleration is available).</p>
<p>This option only applies to applications running in the standalone
Flash Player. For applications running in a browser, setting
<samp>use-gpu</samp> to <samp>true</samp> is equivalent to setting
<samp>wmode</samp> to <samp>"gpu"</samp> in the HTML wrapper. For AIR
applications, use the <samp>renderMode</samp> application descriptor
tag.</p>
<p>The default value is <samp>false</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>use-network=true|false</code></pre>
</div></td>
<td><p>Specifies that the current application uses network services.</p>
<p>The default value is <samp>true</samp>.</p>
<p>When the <samp>use-network</samp> property is set to
<samp>false</samp>, the application can access the local filesystem (for
example, use the <samp>XML.load()</samp> method with file: URLs) but not
network services. In most circumstances, the value of this property
should be <samp>true</samp>.</p>
<p>For more information about the <samp>use-network</samp> property, see
<a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7f9b.html">Security</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>use-resource-bundle-metadata=true|false</code></pre>
</div></td>
<td><p>Enables resource bundles. Set to <samp>true</samp> to instruct
the compiler to process the contents of the
<samp>[ResourceBundle]</samp> metadata tag.</p>
<p>The default value is <samp>true</samp>.</p>
<p>For more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fcf.html">Resource
Bundles</a>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>verbose-stacktraces=true|false</code></pre>
</div></td>
<td><p>Generates source code that includes line numbers. When a run-time
error occurs, the stacktrace shows these line numbers.</p>
<p>Enabling this option generates larger SWF files.</p>
<p>Enabling this option does not generate a debug SWF file. To do that,
you must set the <samp>debug</samp> option to <samp>true</samp>.</p>
<p>The default value is <samp>false</samp>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>verify-digests=true|false</code></pre>
</div></td>
<td><p>Instructs the application to check the digest of the RSL SWF file
against the digest that was compiled into the application at compile
time. This is a security measure that lets you load RSLs from remote
domains or different sub-domains. It also lets you enforce versioning of
your RSLs by forcing an application's digest to match the RSL's digest.
If the digests are out of sync, you must recompile your application or
load a different RSL SWF file.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>version</code></pre>
</div></td>
<td><p>Returns the version number of the MXML compiler. If you are using
a trial or Beta version of Flex, the version option also returns the
number of days remaining in the trial period and the expiration
date.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>warn-warning_type=true|false</code></pre>
</div></td>
<td><p>Enables specified warnings. For more information, see <a href="../viewing-errors-and-warnings.md">Viewing warnings
and errors</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>warnings=true|false</code></pre>
</div></td>
<td><p>Enables all warnings. Set to <samp>false</samp> to disable all
warnings. This option overrides the
<samp>warn-</samp><em><samp>warning_type</samp></em> options.</p>
<p>The default value is <samp>true</samp>.</p></td>
</tr>
</tbody>
</table>

The following sections provide examples of using the mxmlc application compiler
options on the command line. You can also use these techniques with the
application compiler in Flash Builder.
