AlphaOS
=======
This is an OS developed by me, Cryptix, it is my first real major dcpu-16 coding project. The purpose of this project is mainly to get some real coding
experience under my belt and for fun. This OS features full drivers that can handle multiple devices of a single type, 
libraries, managers, it's own filesystem, and eventualy, a menu style gui.

Changelog:
v0.1 added all folders, dasm files(the start of the drivers, libraries, managers, .defines, file allocation, and AlphaOSmain), and Text files.
v0.2 finished clock, keyboard, lem1802, m35fd, spc2000, and sped-3 drivers.
v0.3 coded interrupt manager, started libraries such as math, string, memory, ect..
v0.4 finished Libraries.
v0.5 started coding the Filedriver and GUI.
v0.6 finished the m35fd driver multisector read/write error checks. finished BitLib. 
v0.7 Rearanged text files and start rewriting the filedriver.

Next (planned): 
v0.8 finish coding the filedriver and GUI

NOTES:
1.  On the Hardware and Interrupt manager:
	Because the interrupt manager uses each byte of an interrupt message as a separate piece of data* then there is a hard limit of 256 possible interrupting
	devices (clock 1 vs. clock 2) and a hard limit of 256 possible interrupting device types (clocks vs. keyboards) making a total of 65,536 possible connected 
	interrupting devices (interrupts from software count as a single interrupting hardware type with 256 possible messages).
2.  On the filesystem and file extensions:
	File extensions have no names, nor should they. A file extension should always have it's filedata on a folder/root table immediately after it's parent file. 
	It should be treated exactly the same as it's parent file, so when the parent is deleted then the extension gets deleted, when the parent gets moved/loaded/unloaded
	then so does the extension. Also, folders should never have extensions.

*The messages are formatted as such: aaaaaaaabbbbbbbb a=message source (specifies the hardware type. e.g. if a=1 then a clock sent the message)  
 b=message num (specifies the specific hardware device of that sent the message. e.g. if b=1 then clock 1 set the message).
 
Credits:
Notch: for starting it all
Entropy/ChaOS: Inspiration
Herobrine (http://0x10cforum.com/profile/2063911): For making the Emulator, DevCPU, in which this OS is coded.
Cryptix (http://www.0x10cforum.com/profile/2423132): Coded everything and helped design Filesystem
Fen-ok (http://www.0x10cforum.com/profile/4855939): Helped design Filesystem
KillaVanilla (http://www.0x10cforum.com/profile/4054353): I used some of his code in Math.lib.dasm

