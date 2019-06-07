Be.HexEditor
============

This repository mirrors source code of [Be.HexEditor](http://sourceforge.net/projects/hexbox/) project created by Bernhard Elbl.


Bug in Visual Studio: 
File Be.HexEditor\Be.HexEditor\FormHexEditor.resx

Invalid value Ctrl+0 

Invalid ResX-File. 
The requested value "Ctrl" could not be found. Line 130, Position 5.	

Ungültige ResX-Datei. 
Der angeforderte Wert "Ctrl" konnte nicht gefunden werden. Zeile 130, Position 5.	



<value>Ctrl+O</value>
==>
<value>Strg+O</value>


WTF ? 
Why is it using current-culture to read keyboard-keys from XML ? ...
This only ever works in ONE language...

https://developercommunity.visualstudio.com/content/problem/29523/problems-with-shortcuts-eg-ctrl-p-in-resx-files-wh.html
reported Mar 14, 2017 at 09:00 AM

Sure, the window 10 runs in German language. 
If I change all Ctrl to Strg, it works, but this is not the right solution.

@Paweł Dyda: Visual Studio creates correct *.resx files.
@Paweł Dyda: Well, it creates correct *.resx files, but it reads them incorrectly. 
For example, it saves <value>Ctrl+O</value>, but if the OS is German, 
it can only read the key if the value is "<value>Strg+O</value>". 
And I consider the resulting fact, that a correct source code can only be compiled 
on an english operating system as an a bit questionable approach ... 

so if I change the source code to work with a German OS, it won't compile on an English OS anymore... 
