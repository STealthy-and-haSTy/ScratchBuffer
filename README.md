Scratch Files
-------------

Often, when helping people out with problems they might be having it is handy
to come up with a code sample or simply play around with sample text. Although
it is simple to create a new view and set the syntax using a keystroke and the
command palette, that leaves you with a file that you get asked to save when
you probably don't care.

This simple package adds a command that creates a view, sets the appropriate
syntax and marks it as a scratch buffer so that it can be closed with impunity.

An event listener catches a save on the scratch buffer and turns off the
scratch setting so that the buffer becomes an ordinary file buffer again,
stopping you from losing any work if you decide your scratch file should be
more permanent.

The package presents you with an easily browse-able list of available syntaxes
in an easy to sort list, allowing you to quickly dial in to get the syntax that
you need:

![Command Palette Sample](https://github.com/STealthy-and-haSTy/ScratchBuffer/blob/master/command-palette.png?raw=true)

It's also possible via key bindings or custom command palette entries to create
buffers with any syntax you like.


-------------------------------------------------------------------------------


## Installation ##

### Package Control ###

The best way to install the package is via PackageControl, as this will take
care of ensuring that the package is kept up to date without your having to do
anything at all.

To install via Package Control, open the Command Palette and select the command
`Package Control: Install Package` and search for `ScratchBuffer`.


### Manual Installation ###

In order to manually install the package, clone the repository into your
Sublime Text `Packages` directory. You can locate this directory by choosing
`Preferences > Browse Packages...` from the menu.

Manual installation is not recommended for most users, as in this case you are
responsible for manually keeping everything up to date. You should only use
manual installation if you have a very compelling reason to do so and are
familiar enough with the process to know how to do it properly.


-------------------------------------------------------------------------------


### Usage ###

The package includes a command palette entry `ScratchBuffer: Prompt For Syntax`
that will allow you to easily select the syntax for a scratch buffer and create
one quickly and easily. There are also some command palette entries for some of
the more commonly used syntax definitions which you can use directly or bind to
a key.

The package implements a command named `scratch_buffer` that does the work; if
you pass it a `syntax` argument, it will directly create a scratch buffer using
the syntax you provide:

```json
    {
      "keys": ["super+p"], "command": "scratch_buffer",
      "args": { "syntax": "Packages/Python/Python.sublime-syntax" }
    },
```

If no `syntax` argument is given, you will be prompted to select the syntax to
use from a fuzzy searchable list; each syntax is annotated with an `S` if it is
a syntax that Ships with Sublime and an `I` if it is a syntax from an Installed
package.


-------------------------------------------------------------------------------


## Configuration ##

The following configuration options are available for ScratchBuffer. You can
see the default settings as well as your own custom settings under the
`Preferences > Package Settings > ScratchBuffer` menu entries or via the
command palette with `Preferences: ScratchBuffer Settings`. On MacOS, the
`Preferences` menu is under `Sublime Text` in the menu.


### `show_hidden_syntaxes`: true/false (Default: false) ###

Some packages (including those that ship with Sublime Text itself) contain
syntax definitions that are marked as `hidden` so that they don't appear in
menus.

This setting (which defaults to `false`) allows you to show those syntaxes in
the list when creating a scratch buffer.


-------------------------------------------------------------------------------


## License ##

Copyright 2022 Terence Martin

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
