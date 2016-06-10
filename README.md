# Finsal
A BASH script that aides in the creation of self contained, self extractable, BASH scripts

# Why would I ever need this?
"Why wouldn't I need this?" is a much better question! Or maybe it isn't. 

Have you ever been in the situation where you wanted to bundle your own software and thought to yourself "RPMs and DEBs are sooooo complicated! And I don't have to tools to build them! And my userbase doesn't have the required computer skills to unzip/untar a file and run the included shell script!"? If you've ever found yourself in this situation, then Finsal might just be for you!

Finsal allows you to bundle ANY file types inside of a BASH script, then execute a script among those files you bundled. Neat, right?

# How does this magic work?!
It's pretty simple, but also kind of cool. Essentially Finsal contains a decompression script within it (this is important, remember it for later). When executed, Finsal will compress your files, then write the decompression script out to a .jsh file. Next, it takes your compressed folder of files, and cats it back into the decompression script it just wrote out. Cool! But we aren't done yet. The decompression script uses awk to determine that your .tar.gz that was delicately written as text to the bottom of itself, exists and gunzip/untars the text as real files. Next the decompression script looks for, and runs your "installer" file, so that the installer can do it's thing. Finally, the decompresion script cleans up after itself, and closes.

