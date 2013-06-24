How to use Help in vim

If you are stuck at any place and you need some help you can get it easily by using the following help command, but remember if you want to use this command, first of all get out from your current mode to the normal mode, by pressing ESC then write the following command.  

:help 

:h

Its actually help.txt file which will open with many help topics and you will find the resolution of your problem in it. You can move your cursor down by pressing the down arrow key to check all the help topics. 

How to search words in help file:
If you want to search something in help file of vim, use the following command for it. We will search “quick” in following command, after writing the following command we need to press “Ctrl+D” to run the following search command. (Remember: if you will press Enter after writing the following command it will not be executed).  
:help quick 

 


Search Results of our search command. 

 

When you see your search results, use “Tab” key to switch between the topics in your search results and press Enter to open any topic related to your query. 
 
Some Basic Commands to use in Vim
We are running vim on our Ubuntu server, so in terminal mode we need to work with commands. Following are some basic but very useful commands to start working on vim. 
Command	Purpose ( What does it do)

Vim	To start vim
i	To go to insert mode

Esc	To exit from any mode you are in, or go to command mode

:q	To quit the file or to quit vim

:q!	To quit without saving file

:help 	To open the help file

:help keyword	to search ‘keyword’ from help file (after writing keyword press Ctrl+D to execute the command, if you press Enter it will not be executed 

:w	Save changes

:wq	Save changes and exit

:w filename	To save your text in file ‘filename’


If we will use the following commands in insert mode we will have to hold “Alt” key, for example Alt+w or Alt+b.

w	To go to the initial character of next word

b	To go to the initial character of the previous word

e	To go to the last character of next word

0	To go to the start of the line

$	To go to the end of the line press 

u	Undo

Ctrl+r	Rdo
/search	To search any word in our text, “search” is our keyword which we are searching in this command.
#	To find the previous occurrence of the word in our text
*	To find the next occurrence of the word in our text
*	
e	To the end of the word in insert mode

b	To the beginning of the word
 
0	To the beginning of the line

$	To the end of the line

i	Insert before cursor.

I	Insert to the start of the current line.

a	Append after cursor.

A	Append to the end of the current line.

H	To the first line of the screen.

M	To the middle line of the screen.

L	To the the last line of the screen.

Reference: http://www.tuxfiles.org/linuxhelp/vimcheat.html

