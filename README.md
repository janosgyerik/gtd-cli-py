Acknowledgements
================
This software was written by Steve Butler, called "iKog". 

Project homepage: https://sites.google.com/site/henspace/ikog

Author blog: http://cuckooswearblack.blogspot.com/

Author twitter: http://twitter.com/henspace

About
-----
Welcome to the iKog program.  This is a very simple utility designed to make the management of your to-do lists quick and easy.  The emphasis is on speed and portability.  The program is a text-only utility with no graphical user-interface but it does include some features specifically designed to help with techniques such as Getting Things Done (GTD).  If you're looking for fancy menus and windows, then iKog is not for you.  If you're comfortable with text-based applications, then perhaps you'll find it useful.  Anyway its free, so you've got nothing to lose.

Getting started
---------------
- Add a task

        >>>+ Learn how to use this program.

- Add another task

        >>>+ Read that book on web design.

- Add another task but this time with a priority of 8. i.e quite important.

        >>>+ Buy tin or red paint for the bathroom #8

- Add another task, priority 7 and put it in a project called Bathroom

        >>>+ Buy ceramic tiles #7 :pBathroom

- Add a task that I want to put in a context list of jobs I can do at the computer.

        >>>+ Search the web for a pasta recipe @computer

- Add another task that I can do at the computer but use the abbreviated form.

        >>>+ Buy a book from Amazon @c

- Add a task that must be done on 30th August 2006

        >>>+ Take the cat to the vets :d2006-08-30

- List all of my tasks.

        >>>list
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
        [00] Buy tin of read paint for the bathroom #8 @Anywhere [2006-08-17]
        [01] Buy ceramic tiles #7 @Anywhere Projects: Bathroom [2006-08-17]
        [02] Learn how to use this program #5 @Anywhere [2006-08-17]
        [03] Read that book on web design #5 @Anywhere [2006-08-17]
        [04] Search the web for a pasta recipe #5 @Computer [2006-08-17]
        [05] Buy a book from Amazon #5 @Computer [2006-08-17]
        [06] @Date 2006-08-30 Take the cat to the vets #5 @Anywhere [2006-08-17
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- List only the tasks that I can do at the computer.

        >>>list @c
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
        Filter = @Computer
        [04] Search the web for a pasta recipe #5 @Computer [2006-08-17]
        [05] Buy a book from Amazon #5 @Computer [2006-08-17]
        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- Produce a list, grouped by context

        >>>@

- Produce a list, grouped by context, saved in %prog.html and open in a browser

        >>>@>

- Okay, I've bought that book from Amazon, lets get rid of it.

        >>>kill 5

- I want to put task 4, searching the web, into an @Internet context instead of the @Computer context.

        >>>mod 4 @internet

- Go to the next task in my list.

        >>>next

- Get help.

        >>>help

General commands
----------------
<pre>
?                  : displays a quick reference card
HELP/H             : displays this help.
VERSION/VER        : display the version.
WEB                : Go to the website for more information
CLEARSCREEN/CLS    : Clear the screen
COLOR/COLOUR/C [N] : Use colour display (not Windows) N=1 for no background
MONOCHROME/MONO    : Use monochrome display
EXPORT             : Export the tasks only to filename.tasks.txt
IMPORT file        : Import tasks from the file
REVIEW/REV ON|OFF  : If on, hitting enter moves to the next task
                   : If off, enter re-displays the current task
V0                 : Same as REVIEW OFF
V1                 : Same as REVIEW ON
SAVE/S             : Save the tasks
O/OPEN file        : Open a new data file.
NEW file           : Create a new data file.
AUTOSAVE/AS ON|OFF : Switch autosave on or off
SYS ON|OFF         : Allow the program to use system calls.
!CMD  command      : Run a system command.
2                  : Start a two minute timer (for GTD)
QUIT/Q             : quit the program
</pre>

Task entry and editing commands
-------------------------------
<pre>
For the editing commands that require a task number, you can
replace N by '^' or 'this' to refer to the current task.
ADD/A/+ the task   : add a task to the bottom of the list.
                   : Entering any line that does not begin with
                   : a valid command and which is greater than 10
                   : characters long is also assumed to be an addition.
EDIT/ED [N]        : Create task, or edit task N, using external editor.
SUB/SU N /s1/s2/   : Replace text s1 with s2 in task N. Use \/ if you
                   : need to include the / character.
NOTE/NOTES text    : shorthand for ADD #0 @Notes text
IMMEDIATE/I/++     : add a task to the top of the list to do today.
REP/R N [text]     : replace task N
MOD/M N [text]     : modify task N.
EXTEND/E N [text]  : add more text to task N
FIRST/F N          : move task N to the top.
DOWN/D/ N          : move task N down the queue
UP/U/ N            : move task N up the queue
</pre>

Task removal commands
---------------------
<pre>
KILL/K/X/- N       : kill (delete) task N. You must define N
DONE N [text]      : Remove task N and move to an archive file
ARCHIVE N [text]   : Same as DONE
CLEAR              : Remove all tasks
</pre>

Display commands
----------------
<pre>
SHOW N             : display encrypted text for task N
FILTER/FI [filter] : set a filter.  Applies to all displays
                   : See list for details of the filter
                   : Setting the filter to nothing clears it.
TOP/T [N]          : Go to top, list N tasks, and display the top task
NEXT/N             : display the next task. Same as just hitting enter
PREV/P             : display previous task
GO/G N             : display task N
LIST/L [filter]    : list tasks. Filter = context, project, priority, date
                   : or word. Contexts begin with @ and projects with :p
                   : Dates begin with :d, anything else is a search word.
                   : Precede term with - to exclude e.g.  -@Computer
                   : e.g LIST @computer or LIST #5
@                  : sorted list by Context.
:D                 : sorted list by Dates
:P                 : sorted list by Projects
LIST>/L> [filter]  : standard list sent to an HTML report
@>                 : sorted list by Context sent to an HTML report
:D>                : sorted list by Dates sent to an HTML report
:P>                : sorted list by Projects sent to an HTML report
                   : The HTML reports are sent to todoFilename.html
</pre>

Advanced options
----------------
<pre>
The SETEDxxx commands allow you to use an external editor.
Note the editor you pick should be a simple text editor.  If you pick
something that doesn't work, try the defaults again.
Because some systems may have different editors installed, you can set
more than one by separating the editors usng commas.  The program will
use the first one it finds.
For Windows the default is edit, which works quite well in the terminal
but you could change it to notepad.
For Linux, the default is nano,pico,vim,emacs.
To use external editors you must switch on system calls using the SYS ON
command
SETEDNT command    : Set the external editor for Windows (NT).
SETEDPOSIX command : Set the editor for posix systems.
                   : e.g. SETEDNT edit
                   :      SETEDPOSIX nano,vim
SHORTCUT/SC ?      : list shortcuts
SHORTCUT/SC N cmd  : Set shortcut N to command cmd
=N                 : Run shortcut N
ABBREV/AB @x @full : Create new abbreviation. @x expands to @full
ABBREV/AB ?        : List context abbreviations.
PAB :px :pfull     : Project abbreviation. :px expands to :pfull
PAB ?              : List project abbreviations.
</pre>

Contexts
--------
<pre>
Any word preceded by @ will be used as a context.  Contexts are like
sub-categories or sub-lists.  There are a number of pre-defined
abbreviations that you can use as well. The recognised abbreviations
are:
@A = @Anywhere (this is the default)
@C = @Computer
@D = @Desk
@E = @Errands
@H = @Home
@I = @Internet
@L = @Lunch
@M = @Meeting
@N = @Next
@O = @Other
@P = @Phone
@PW= @Password
@S = @Someday/maybe
@W4= @Waiting_for
@W = @Work
</pre>

Entering dates
--------------
<pre>
An @Date context is created if you embed a date in the task.
Dates are embedded using the :dDATE format.
Valid DATE formats are yyyy-mm-dd, mm-dd or dd
You can also use : or / as the separators.  So, for example:
:d2006/12/22 or :d2006-11-7 or :d9/28 are all valid entries.

If you set a date, then until that date is reached, the task is given
an effective priority of 0.  Once the date is reached, the task's
priority is increased by 11, moving it to the of the list.

A date entry of :d0 can be used to clear a date entry.
A date entry of :d+X can be used to create a date entry of today + X days.
So :d+1 is tomorrow and :d+0 is today.
</pre>
