  
  
**pyro**
[index](.)  
[/home/twitch/media/Documents/python/virts/pyro/pyro](file:/home/twitch/media/
Documents/python/virts/pyro/pyro)

`simple elegant text editor built on python/tkinter  
by James Stallings, June 2015  
  
Adapted from:  
  
  Pygments Tkinter example  
  copyleft 2014 by Jens Diemer  
  licensed under GNU GPL v3  
and  
  
  'OONO' designed and written by Lee Fallat, 2013-2014.  
  Inspired by acme, sam, vi and ohmwriter.  
  
A sincere thanks to these good people for making their source code available
for myself and others  
to learn from. Cheers!  
  
  
    Pyro currently does a very minimalist job of text editing via tcl/tk ala tkinter.   
    What pyro does now:  
       colorizes syntax for a variety of text types; to wit:  
  
           Python  
           PlainText  
           Html/Javascript  
           Xml  
           Html/Php  
           Perl6  
           Ruby  
           Ini/Init  
           Apache 'Conf'  
           Bash Scripts  
           Diffs  
           C#  
           MySql  
       writes out its buffer  
       converts tabs to 4 spaces  
  
       It does this in an austere text editor framework which is essentially a glue layer  
       bringing together the tk text widget with the Pygment library for styling displayed  
       text. Editor status line is in the window title.  
       Pyro comes with one serious warning: it is a user-space editor. It makes no effort  
       to monitor state-change events on files and so should not be used in situations  
       where it is possible that more than one writer will have access to the file.  
    Pyro's current controls are as follows:  
       Ctrl+q quits  
       Ctrl+w writes out the buffer  
       Selection, copy, cut and paste are all per xserver/window manager. Keyboard navigation via  
       arrow/control keys, per system READLINE.  
    Pyro's current commands are:  
       #(num) move view to line 'num' and highlight it, if possible.  
       *(text) find text in file.  
       /(delim)(text)(delim)(text) search and replace  
    Pyro requires Tkinter and Pygment external libraries.`

  
**Modules**

`      `



[_tkinter](_tkinter.html)  
[tkinter.font](tkinter.font.html)  

[io](io.html)  
[os](os.html)  

[tkinter.scrolledtext](tkinter.scrolledtext.html)  
[sys](sys.html)  

[tkinter](tkinter.html)  
[tkinter.ttk](tkinter.ttk.html)  

  
**Classes**

`      `



[builtins.object](builtins.html#object)

[CoreUI](pyro.html#CoreUI)

  
class **CoreUI**([builtins.object](builtins.html#object))

`   `

`CoreUI is the editor [object](builtins.html#object), derived from class
'[object](builtins.html#object)'. It's instantiation initilizer requires the  
ubiquitous declaration of the 'self' reference implied at call time, as well
as a handle to  
the lexer to be used for text decoration.  
 `



Methods defined here:  

**__init__**(self, lexer)

**autoindent**(self, event)
    `this method implements the callback for the Return Key in the editor widget.  
arguments: the tkinter event [object](builtins.html#object) with which the
callback is associated`

**close**(self, event=None)
    `this event callback method implements the Quit operation (ctrl+q). In a perfect   
world, it will check on whether the file is saved and warn the user
accordingly  
a graceful way out.  
arguments: the associated event argument. However, unlike the other event  
callbacks in the code, this one may be called without an associated event
[object](builtins.html#object)  
as it will discard everything.`

**cmd**(self, cmd, index_insert)
    `this method parses a line of text from the command line and invokes methods on the text  
as indicated for each of the implemented commands  
arguments: the command, and the insert position`

**cmdcleanup**(self, index_start, index_end)
    `this method cleans up post-command and prepares the command line for re-use  
arguments: index beginning and end. ** this needs an audit, as does the entire  
                                        index start/end construct **`

**cmdlaunch**(self, event)
    `this method implements the callback for the key binding (Return Key)   
in the command line widget, wiring it up to the parser/dispatcher method.  
arguments: the tkinter event [object](builtins.html#object) with which the
callback is associated`

**create_tags**(self)
    `thmethod creates the tags associated with each distinct style element of the   
source code 'dressing'`

**destroy_window**(self)
    `this method safely closes the window`

**event_key**(self, event)
    `this method traps the keyboard events. anything that needs doing when a key is pressed is done here.  
arguments: the associated event [object](builtins.html#object)`

**event_mouse**(self, event)
    `this method traps the mouse events. anything that needs doing when a mouse  
operation occurs is done here.  
arguments: the associated event [object](builtins.html#object)`

**event_write**(self, event)
    `the callback method for the root window 'ctrl+w' event (write the file to disk)  
arguments: the associated event [object](builtins.html#object).`

**gotoline**(self, linenumber)
    `this method implements the core functionality to locate a specific line of text by  
line position  
arguments: the target line number`

**loadfile**(self, text)
    `this method implements loading a file into the editor.  
arguments: the scrollable text [object](builtins.html#object) into which the
text is to be loaded`

**mainloop**(self)
    `the classical tkinter event driver loop invocation, after running through any   
startup tasks`

**recolorize**(self)
    `this method colors and styles the prepared tags`

**replace**(self, regexp, subst, cp)
    `this method implements the search+replace compliment to the search functionality`

**search**(self, regexp, currentposition)
    `this method implements the core functionality of the search feature  
arguments: the search target as a regular expression and the position  
from which to search.`

**tab2spaces4**(self, event)
    `this method implements the callback for the indentation key (Tab Key) in the  
editor widget.  
arguments: the tkinter event [object](builtins.html#object) with which the
callback is associated`

**uiconfig**(self)
    `this method sets up the main window and two text widgets (the editor widget, and a   
text entry widget for the commandline).`

**updatetitlebar**(self)
    `this method updates the status information in the window title`

* * *

Data descriptors defined here:  

**__dict__**
    `dictionary for instance variables (if defined)`

**__weakref__**
    `list of weak references to the object (if defined)`

