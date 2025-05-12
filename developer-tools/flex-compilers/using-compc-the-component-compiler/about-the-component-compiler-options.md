# About the component compiler options

The component compiler options let you define settings such as the classes,
resources, and namespaces to include in the resulting SWC file.

The component compiler can take most of the application compiler options, and
the options described in this section. For a description of the application
compiler options, see
[About the application compiler options](../using-mxmlc-the-application-compiler/about-the-application-compiler-options.md).
Application compiler options that do not apply to the component compiler include
the metadata options (such as `contributor`, `title`, and `date`), default
application options (such as `default-frame-rate`), `locale`, `debug-password`,
and `theme`.

The component compiler has compiler options that the application compilers do
not have. The following table describes the component compiler options that are
not used by the application compilers:

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
<pre><code>compute-digest=true|false</code></pre>
</div></td>
<td><p>Writes a digest to the catalog.xml of a library. Use this when
the library will be used as a cross-domain RSL or when you want to
enforce the versioning of RSLs. The default value is true.</p>
<p>For more information about RSLs, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>directory=false|true</code></pre>
</div></td>
<td><p>Outputs the SWC file in an open directory format rather than a
SWC file. You use this option with the <samp>output</samp> option to
specify a destination directory, as the following example shows:</p>
<div>
<pre><code>compc -directory=true -output=destination_directory</code></pre>
</div>
<p>You typically use this option when you create RSLs because you must
extract the library.swf file from the SWC file before deployment. For
more information, see <a
href="WS2db454920e96a9e51e63e3d11c0bf69084-7fd1.html">Runtime Shared
Libraries</a>.</p>
<p>The default value is false.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>include-classes class [...]</code></pre>
</div></td>
<td><p>Specifies classes to include in the SWC file. You provide the
class name (for example, MyClass) rather than the file name (for
example, MyClass.as) to the file for this option. As a result, all
classes specified with this option must be in the compiler's source
path. You specify this by using the <samp>source-path</samp> compiler
option.</p>
<p>You can use packaged and unpackaged classes. To use components in
namespaces, use the <samp>include-namespaces</samp> option.</p>
<p>If the components are in packages, ensure that you use dot-notation
rather than slashes to separate package levels.</p>
<p>This is the default option for the component compiler.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>include-file name path [...]</code></pre>
</div></td>
<td><p>Adds the file to the SWC file. This option does not embed files
inside the library.swf file. This is useful for adding graphics files,
where you want to add non-compiled files that can be referenced in a
style sheet or embedded as assets in MXML files.</p>
<p>If you add a stylesheet that references compiled resources such as
programmatic skins, use the <samp>include-stylesheet</samp> option.</p>
<p>If you use the <samp>[Embed]</samp> syntax to add a resource to your
application, you are not required to use this option to also link it
into the SWC file.</p>
<p>For more information, see <a
href="./adding-nonsource-classes">Adding nonsource
classes</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>include-lookup-only=false|true</code></pre>
</div></td>
<td><p>If <samp>true</samp>, only manifest entries with
<samp>lookupOnly=true</samp> are included in the SWC catalog. The
default value is <samp>false</samp>.</p>
<p>This is an advanced option.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>include-namespaces uri [...]</code></pre>
</div></td>
<td><p>Specifies namespace-style components in the SWC file. You specify
a list of URIs to include in the SWC file. The uri argument must already
be defined with the <samp>namespace</samp> option.</p>
<p>To use components in packages, use the <samp>include-classes</samp>
option.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>include-sources path-element</code></pre>
</div></td>
<td><p>Specifies classes or directories to add to the SWC file. When
specifying classes, you specify the path to the class file (for example,
MyClass.as) rather than the class name itself (for example, MyClass).
This lets you add classes to the SWC file that are not in the source
path. In general, though, use the <samp>include-classes</samp> option,
which lets you add classes that are in the source path.</p>
<p>If you specify a directory, this option includes all files with an
MXML or AS extension, and ignores all other files.</p>
<p>If you use this option to include MXML components that are in a
non-default package, you must include the source folder in the source
path.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>include-stylesheet namepath [...]</code></pre>
</div></td>
<td><p>Specifies stylesheets to add to the SWC file. This option
compiles classes that are referenced by the stylesheet before including
the stylesheet in the SWC file.</p>
<p>You do not need to use this option for all stylesheets; only
stylesheets that reference assets that need to be compiled such as
programmatic skins or other class files. If your stylesheet does not
reference compiled assets, you can use the <samp>include-file</samp>
option.</p>
<p>This option does not compile the stylesheet into a SWF file before
including it in the SWC file. You compile a CSS file into a SWF file
when you want to load it at run time.</p></td>
</tr>
</tbody>
</table>

On the command line, you cannot point the compc utility to a single directory
and have it compile all components and source files in that directory. You must
specify each source file to compile.

If you have a large set of components in a namespace to include in a SWC file,
you can use a manifest file to avoid having to type an unwieldy compc command.
For information on creating manifest files, see
[About manifest files](../about-manifest-files.md).

The following sections describe common scenarios where you could use the compc
command-line compiler. You can apply the techniques described here to compiling
SWC files in Flash Builder with the Flex Compiler.
