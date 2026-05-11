# Chp 2: Editing Little Faster

## Word Movement
> w : Move the word faster. As like many other commands you can use numeric prefix to move past multiple words. For eg. 4b moves back four words.
> b : Move the word backward. As like many other commands you can use numberic prefix to move past multiple words. For eg. 4b moves back four words.
> $ : Moves the cursor to end of the line. These command take numeric argument as well for eg. 1$ => end of the current line.
	2$ => end of next line
> ^ : Moves the cursor to first non-blank character of the line.
> 0 : Moves the cursor to absolute start of the line.
	You can specify the numberic argument with above two command but they do not do anything with it.
	
## Searching Along a Single Line
> fx (forward Search) : Searches the line for the single character x in the right side.
	You can specify a count. Therefore, you can space forward five words by using the command 5f<Space>. This only moves five space characters.
	not five words. IF there are multiple spaces between wordsk, this will not move five words!

> Fx : Searches the line for the single charcter x but in the left side.

> tx : Works same as fx but it stops one character before indicated character.

> Tx : Simply the backward version of tx.

Sometimes you will start a search, only to realize that you have typed the wrong com-
mand.You type f to search backward, for example, only to realize that you really
meant F.To abort a search, press <Esc> as the search key. So f<Esc> is an aborted for-
ward search. (Note: <Esc> cancels most operations, not just searches.)

## Moving to Specific Line
> G : Position you to the end line of the file. 
	It can also take argument, If you gave argument it will positions you at the given line number.
	For eg. 3G puts you on line 3. (Likewise, use the 1G command to go to the top of the file rather than 9999k).


## Telling Where You are in a File
> :set number : Set the line numbering.

> :set nonumber : Turn off the line numbering.

> CTRL + G : Display a status line that indicates where you are in the file. For example ""readme.md" [Modified] 39 lines --100%--"
	This indicates that you are editing a file called readme.md, and that it has been modified since the editing started.
	The cursor is positioned on line 39 out of total 39 or about 100% of the way through the file.Th cursor is currently siting in the last column.

	Sometimes you will see a split column number (for example, col 2–9).This indi-
	cates that the cursor is positioned on character 2. But because character one is a tab,
	the screen column is 9. Figure 2.8 shows the results of a typical CTRL-G command.


# Scrolling Up and Down
> CTRL + D : move Down half a screen
	scrolls the page downward
	cursor also moves downward

> CTRL + U: move Up half a screen
	scrolls upward
	cursor also moves upward

| Command    | Action                 |
| ---------- | ---------------------- |
| `Ctrl + D` | half-page down         |
| `Ctrl + U` | half-page up           |
| `Ctrl + F` | full page forward      |
| `Ctrl + B` | full page backward     |
| `zz`       | center current line    |
| `zt`       | current line to top    |
| `zb`       | current line to bottom |


## Deleting Text
> dd : Deletes a line.

> dw : Deletes a word.
	In fact, the d command may be followed by any motion command, and it deletes from the current location
	to the place where the cursor winds up. (Therefore, we say the syntax of  the d command is dmotion)
	e.g The 3w commands, for example, moves the cursor over three words. The d3w or 3dw mand deletes three words.

> D : Shortcut for d$. Delete the content on the line starting from the current position.

3dw
Count applies to the whole command.
(3 times) × (delete 1 word)

d3w
Count applies only to the motion.
delete (move 3 words)

Now the interesting part: 3d2w
3d2w
Break it:
3   d   2w
↑       ↑
repeat  move 2 words
Meaning:
d2w → delete 2 words
Repeat that 3 times
So total:
2 × 3 = 6 words
deleted.


## Changing Text
> c : It acts like the d command, except it leaves you in insert mode.
	The cmotion command works just like the dmotion command, with one exception: the cw and dw
	commands.Whereas cw deletes the text up to the space following the word (and then
	enters insert mode), the dw command deletes the word and the space following it.

+--------------------------------------------------+
|                cwscrew<Esc>                      |
+--------------------------------------------------+
                  ││    │
                  ││    └── <Esc>  : Ends insert mode
                  │└────── screw   : Inserted word
                  └─────── w       : Change one word

c : Change command

> cc : It deletes the line and goes into the insert mode.

> c$ or C : Changes from the cursor to the end of the line.

## The . Command
> . : Repeat the last change. Change: insert, delete, replace, paste, change word, etc.
	e.g repeat delete: 
	Text: one two three four
	Command: dw
	Delete one
	Now text: two three four
	Move cursor to three and press:
	.
	Result: two four


	e.g repeat insert/change:
	Text: cat dog fish
	Command: cwlion<Esc>
	Changes cat -> lion
	Now move to dog and press:
	.
	Result: lion lion fish

| Original command | `.` repeats                |
| ---------------- | -------------------------- |
| `x`              | delete character           |
| `dw`             | delete word                |
| `cwabc<Esc>`     | replace word with `abc`    |
| `p`              | paste                      |
| `rA`             | replace character with `A` |


## Joining Line
> J : Command joins the current line witht next one. A space is added to the end of the first line to seperate two piece that are joined.
	It also accepted the numberical argument e.g 3J join the three line with space at the end of each line

## Replacing Characters
> rx : Replace the character under the cursor with the x.
	[count]ra replace the count number of char with a.

Special case: <Enter>
Command:
5r<Enter>
does NOT insert 5 newlines.
Instead:
Vim replaces the 5 characters using ONE newline character.


| Command | Meaning                                       |
| ------- | --------------------------------------------- |
| `5rx`   | replace 5 chars with x                        |
| `r5x`   | replace one char with 5, then delete one char |


## Changing Case
> ~ : Command changes a charcter's case. It changes uppercase to lowercase and vice versa. If a count is specified, The count characters are
	changed. 

## Keyborad Macros
Comming soon ...
