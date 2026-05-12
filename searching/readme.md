## Simple Search
> /<string> : The command is used to search for a word (string)
	Any time the cursor jumps to the bottom of the screen and you type
	 something, you must end it with <Enter>.

Note:The characters .*[]ˆ%/\?~$ have special meaning. If you want to use them in
a search you must put a \ in front of them. Example: to find . use the search string\..

e.g /include <Enter>
To find the next include, use the command /<Enter>.
Another way to find the next match is with the n command.

Both the /<Enter> and n commands can have a count specified. If there is a count,
the command searches for the count number of matches from the current location.

## Search History
The search command has a history feature. Suppose, for example, that you do three
searches:
	./one
	./two
	./three
Now you do / and not <Enter> instead <Up> you can ./three will apear. Now you
can either search for other search command by <Up> or press <Enter> to execute 
it.

## Searching Options
> :set h1search : Causes Vim to highlight any strings found matching the search pattern.
> :set noh1search : Turn off the effect of the :set h1search.
> :noh1search : Clear the current highlighting
> :set incsearch : Set incremental search.
	The editor starts searching as soon as you type the first character of 
	the string. Each additional character further refines the search.
> :set noincsearch : Turn of the effect of the :set incsearch
> ? : If you want to search from the bottom and not from the top.
	If you use n now it will go upward. Also called Reverse
	Search.
Suppose you start a forward search for unsigned using the /unsigned command.You
can turn around and search in the reverse direction by using the ? command.The n
command repeats the search in the same direction.The N command reverses the direc-
tion on the search and repeats it.

## Regular Expression
Vim use regular expression to specify what to search for.
> ^ : The begining of line.The expression include matches
	the word include anywhere on the line. But the expression ^include
	 matches the word include only if it is at the beginning of a line.

> $ : The $ character matches the end of a line.Therefore, was$
	 finds the word was only if it is at the end of a line


If you want to search for a line consisting of just the word the, use the regular
expression ^the$.To search for empty lines, use the regular expression ^$.

> . : Match Any Single Character.
	e.g c.m matches a string whose first character is a, whsoe second
	character is anything and the third character is m.
