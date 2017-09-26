# Vim Tips

I collected below some tips on `vim` that I find helpful.

## Configuration

You can configure your `vim` by putting your configuration options and scripts in the `~/.vimrc` file (a hidden file named `.vimrc` in your home directory).  This file will be loaded whenever you starts `vim`.

## Help

In `vim,` the command `:help <topic>` shows help about a particular topic in `vim`.  Example, `:help backup`.

## Backup Files

You can ask `vim` to automatically backup files that you edit.  This has been a life saver for me in multiple  occasions.

In your `~/.vimrc` file, 

```
set backup=on
```

will cause a copy of your file to be save with suffix `~` appended to its name everytime you save.

I prefer not to clutter my working directory, so I set

```
set backupdir=~/.backup
```

and create a directory named `~/.backup` to store my backup files.

The settings above are the default in your `cs2030-i` account.  So if you made changes to a file that you regreted on `cs2030-i`, or if accidentally deleted a file, you can check under `~/.backup` to see if the backup can save you.

## Undo

Since we are on the topic of correcting mistakes, `u` in command mode undo your changes.  Prefix it with a number $n$ to undo $n$ times.  If you regreted your undo, `<CTRL-R>` will redo.

## Syntax Highlighting

If for some reasons, syntax highlighting is not on by default, add this to your `~/.vimrc`:

```
syntax on
```

## Ruler and Numbers

If you prefer to show the line number you are on and the column number you are on, adding the commands to `~/.vimrc`

```
set ruler
```

will display the line number and the column number on the lower right corner.  

You can also add
```
set number
```

to label each line with a line number.

## Jumping to a Line

If the compiler tells you there is an error on Line $x$, you can issue `:<x>` to jump to Line $x$.  For instance, `:40` will go to Line 40.

## Shell Command

If you need to issue a shell command quickly, you don't have to exit `vim`, run the command, and launch `vim` again.  You can use `!`, 

```
:!<command>
```

will issue the command to shell.  E.g.,

```
:!ls
```

You can use this to compile your current file, without exiting `vim`.

```
:!javac %
```

## Abbreviation

You can use the command `ab` to abbreviate frequently typed commands.  E.g., in your `~/.vimrc`, 

```
ab Sop System.out.println("
```

Now, when you type `Sop `, it will be expanded into `System.out.println(" `

## Auto-Completion

You can `<CTRL-P>` to auto-complete.  By default, the auto-complete dictionary is based on text in your current editing buffers.  This is a very useful keystroke saver for long function and variable names.

## Auto-Indent the Whole File

You can `gg=G` in command mode to auto-indent the whole file.  `gg` is the command to go to the beginning of the file.  `=` is the command to indent.  `G` is the command to go to the end of the file.

## Swapping Lines

Sometimes you want to swap the order of two lines of code, in command mode, `ddp` will do the trick.  `dd` deletes the current line, `p` paste it after the current line, in effect swapping the order of the two lines.

## Goto File

Place your cursor on the name of a class (e.g., `Event`), then in command mode, issue the `gf` command (goto file).  `vim` will open `Event.java`.  You can set the `path` to load files from directories other than the current directory.   "Ctrl-^" will get out and back to the previous file.