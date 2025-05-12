# Using fcsh, the Flex compiler shell

The fcsh (Flex Compiler Shell) utility provides a shell environment that you use
to compile applications, modules, and component libraries. It works very
similarly to the mxmlc and compc command line compilers, but it compiles faster
than the mxmlc and compc command-line compilers. One reason is that by keeping
everything in memory, fcsh eliminates the overhead of launching the JVM and
loading the compiler classes. Another reason is that compilation results (for
example, type information) can be kept in memory for subsequent compilations.

This utility is intended to improve the experience of users of the command-line
compilers. If you are using Flash Builder, you do not need to use fcsh. The
Flash Builder tool already uses the optimizations provided by fcsh.

For simple applications, fcsh might not be necessary. But for more complex
applications that you compile frequently, you should experience a significant
performance improvement over using the mxmlc and compc command-line compilers.

When you first compile an application with fcsh, you will not typically notice
any difference in speed between the fcsh and the command-line compilers. This is
because fcsh must load the application model and custom libraries into memory,
just as the command-line compilers would. After that, however, each subsequent
compilation uses the libraries in memory to compile. This reduces the amount of
disk access that the compilers need to perform and should result in shorter
compile times.

The fcsh tool is in the bin directory. For Unix and Mac OS, it is a shell script
called fcsh. For Windows, it is fcsh.exe. You invoke it only from the command
line. The Java settings are managed by the jvm.config file in the bin directory.

## Using fcsh

You invoke fcsh from the command line. You can launch the utility either as an
executable (Windows) or shell command (Unix/Linux/Mac).

1.  Open a command prompt.

2.  Navigate to the {_SDK_root_}/bin directory.

3.  Enter `fcsh` at the command line. Your commands will now be executed within
    the fcsh environment. You will know this if your command prompt becomes
    `(fcsh)`.

Typically, you compile a simple application when you first launch fcsh; for
example:

    (fcsh) mxmlc c:/myfiles/MyApp.mxml

The fcsh utility returns a target id:

    fcsh: Assigned 1 as the compile target id.

You can then refer to the target ids when using subsequent commands inside the
fcsh utility. For example, to compile the previous application with incremental
compilation:

    (fcsh) compile 1

You can enter `help` in the fcsh shell to see a list of available options; for
example:

    (fcsh) help

You can enter `quit` in the fcsh shell to exit fcsh and return to the command
prompt; for example:

    (fcsh) quit

The following example shows that fcsh dramatically reduces compilation time when
compiling the same application multiple times. The first compilation takes 8885
milliseconds. The second takes only 5140 milliseconds:

    (fcsh) mxmlc -benchmark=true flexstore.mxml
    	Total time: 8885ms
    	Peak memory usage: 84 MB (Heap: 58, Non-Heap: 26)
    (fcsh) mxmlc -benchmark=true flexstore.mxml
    	Total time: 5140ms
    	Peak memory usage: 84 MB (Heap: 57, Non-Heap: 27)

In addition, subsequent _full_ compilations of the same application are much
faster, as the following example shows:

    > touch flexstore.mxml

    (fcsh) compile 1
    	Files changed: 1 Files affected: 0
    	Total time: 933ms
    	Peak memory usage: 88 MB (Heap: 62, Non-Heap: 26)
    	flexstore.swf (522456 bytes)
    	Total time: 1102ms
    	Peak memory usage: 77 MB (Heap: 51, Non-Heap: 26)
    (fcsh)

## About fcsh commands

The following table describes the available fcsh commands:

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
<pre><code>clear [id]</code></pre>
</div></td>
<td><p>Removes the target id(s) from memory but saves the target's
*.cache file. If you enter this command without specifying an id
argument, fcsh clears all target ids. For information about cache files,
see <a href="./using-mxmlc-the-application-compiler/about-incremental-compilation.md">About
incremental compilation</a>.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>compile id</code></pre>
</div></td>
<td><p>Uses incremental compilation (without linking) to compile the
specified id. This command uses the same arguments used in previous
compilations. If you try to compile a target that has not changed, fcsh
skips that target.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>compc arg1 [...]</code></pre>
</div></td>
<td><p>Compiles SWC files from the specified sources. This command
returns a target id that you can then pass to other fcsh options. The
target ids are incremented by 1 for each new compilation. If you quit
fcsh and then relaunch it, all targets are cleared and the ids start at
1 again.</p>
<p>This command takes all the same arguments as the compc command-line
compiler. For information about using compc, see <a href="./using-compc-the-component-compiler/index.md">Using compc, the
component compiler</a>.</p></td>
</tr>
<tr class="even">
<td><p><samp>help</samp></p></td>
<td><p>Lists commands. Commands not listed but also supported include
<samp>cp</samp>, <samp>mv</samp>, <samp>rm</samp>, and
<samp>touch</samp>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>info [id]</code></pre>
</div></td>
<td><p>Displays compiler target information such as the source files and
cache file name. If you do not specify a target id, fcsh prints
information for all targets in reverse id order.</p></td>
</tr>
<tr class="even">
<td><div>
<pre><code>mxmlc arg1 [...]</code></pre>
</div></td>
<td><p>Compiles and optimizes the target application or module using the
mxmlc command-line compiler. This command returns a target id that you
can then pass to other fcsh options. The target ids are incremented by 1
for each new compilation. If you quit fcsh and then relaunch it, all
targets are cleared and the ids start at 1 again.</p>
<p>This command takes all the same arguments as the mxmlc command-line
compiler. For information about using mxmlc, see <a href="./using-mxmlc-the-application-compiler/index.md">Using mxmlc, the
application compiler</a>.</p></td>
</tr>
<tr class="odd">
<td><div>
<pre><code>quit</code></pre>
</div></td>
<td><p>Exits the fcsh utility. All data stored in memory is destroyed.
When you relaunch fcsh, you cannot access targets that you created in a
previous session.</p></td>
</tr>
</tbody>
</table>

The fcsh tool also supports the following commands:

- `cp`

- `mv`

- `rm`

- `touch`
