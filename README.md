Download Link: https://assignmentchef.com/product/solved-cs3423-systems-programming-assignment-6
<br>
: Python Scripting




For this assignment, you will use <strong>Python3 </strong>to create an alternative to the <strong><sub>rm </sub></strong>command. This program, <strong>rm.py</strong>, will take an arbitrary number of paths as arguments and, for each argument, move them to <em>∼</em><strong><sub>/rm_trash </sub></strong>. If <em>∼</em><strong><sub>/rm_trash </sub></strong>does not already exist, it should be created. <strong>Hint: </strong>The <strong><sub>shutil </sub></strong>module may prove useful.

<h1>Duplicate Files</h1>

If a file with the same name already exists in <em>∼</em><strong><sub>/rm_trash </sub></strong>, you should append <strong><sub>-1 </sub></strong>to the end of the filename <strong>before any extension(s) if they exist </strong>so that both files are preserved. If a file with the same name in <em>∼</em><strong><sub>/rm_trash </sub></strong>already has <strong><sub>-1</sub></strong>, the new file should be appended with <strong><sub>-2 </sub></strong>and automatically incremented for subsequent copies.

For example, if a file named <strong><sub>file.txt </sub></strong>is removed 4 times, <em>∼</em><strong><sub>/rm_trash </sub></strong>should contain the following four files: <strong>file.txt</strong>, <strong>file-1.txt</strong>, <strong>file-2.txt</strong>, and <strong>file-3.txt</strong>.

<strong>Note: </strong>It is possible that a file being removed will already have a dash and a number at the end of the name. If this is true, you should be sure not modify the original name and only append the counter. For example, if a file named <strong><sub>newfile-1.txt </sub></strong>is deleted twice, <em>∼</em><strong><sub>/rm_trash </sub></strong>should contain <strong>newfile-1.txt </strong>and <strong>newfile-1-1.txt</strong>. <strong>You may assume that there will be no conflicts in file names (e.g., rm.py file-1.txt; rm.py file.txt)</strong>

<h1>Recursion</h1>

Your program should recursively delete files if <strong>any </strong>argument is <strong><sub>-r</sub></strong>. If <strong><sub>-r </sub></strong>is not set, directories should be ignored and your program should print <strong>rm.py: cannot remove ’<em>DIR</em>’: Is a directory </strong>to <strong>STDERR </strong>once for each directory encountered where <strong><em><sub>DIR </sub></em></strong>is the name of the directory.

When deleting recursively, simply move the directory to <em>∼</em><strong><sub>/rm_trash </sub></strong>using the duplicate naming rules as described above and leave the contents alone. You do not need to modify the names of the files <strong>within </strong>the removed directory.

<h1>Paths</h1>

If an argument does <em>not </em>point to a file, your program should print <strong>rm.py: cannot remove ’<em>FILE</em>’: No such file or directory </strong>to <strong>STDERR </strong>once for each invalid argument where <strong><em><sub>FILE </sub></em></strong>is the path given.

When moving a file into <em>∼</em><strong><sub>/rm_trash </sub></strong>you should always place it at the root of the directory. For example, if <strong>/path/to/a/file.txt </strong>is passed as an argument, <strong>file.txt </strong>should be moved to <em>∼</em><strong>/rm_trash/file.txt </strong>and <em>not ∼</em><strong>/rm_trash/path/to/a/file.txt</strong>.

Assignment 6: Python Scripting                                                                                        Page 1 of 2

<h1>Program Execution</h1>

Your program should be invoked as a single Python file (see below) with an <strong>arbitrary </strong>number of arguments representing paths to files (including directories). The <strong><sub>-r </sub></strong>option may be passed as <em>any </em>argument. Some examples are listed below.

<strong>$ rm.py /path/to/some/file ./somefile someotherfile</strong>

<strong>$ rm.py /path/to/some/file ./somefile someotherfile -r $ rm.py -r /path/to/some/file ./somefile someotherfile</strong>

<strong>$ rm.py *.java</strong>

<h1>Extra Credit (10 points)</h1>

For extra credit, create a separate program called <strong><sub>restore.py </sub></strong>which, given a path to where a file <em>used to be </em>before it was removed with <strong><sub>rm.py</sub></strong>, will restore the <em>most recent version</em>.

<strong>Hint: </strong>Consider keeping track of the original and new locations of removed files to handle situations where removed files from different paths have the same name. Note that if you use this strategy, the information will need to persist between executions of <strong><sub>rm.py </sub></strong>and <strong><sub>restore.py</sub></strong>.

Attempts at extra credit will <strong>not be considered </strong>if <strong><sub>rm.py </sub></strong>does not work correctly.

<h1>Assignment Data</h1>

No sample data is included with this assignment as it should work for all files. As always, you should test your program with your own data as well to be sure that it works correctly.

<h1>Program Files</h1>

Your submission will consist of one or two files depending on if you attempt the extra credit:

<ul>

 <li><strong><sub>py </sub></strong>– implementation of rm</li>

 <li><strong>py </strong>– extra credit</li>

</ul>


