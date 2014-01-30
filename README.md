# Project Description

ZBS-torch is a fork of ZeroBrane Studio to get it to work with Torch-7

For an overview of ZeroBrane Studio, see [README-zbs](https://github.com/soumith/zbs-torch/blob/master/README-zbs.md)

* Written in Lua, so easily customizable.
* Small, portable, and cross-platform (Windows, Mac OSX, and Linux).
* Auto-completion for functions, keywords, and custom APIs.
* Interactive console to directly test code snippets with local and remote execution.
* Integrated debugger with local and [remote debugging](http://studio.zerobrane.com/doc-remote-debugging.html) for Lua 5.1,
[Lua 5.2](http://studio.zerobrane.com/doc-lua52-debugging.html),
[LuaJIT](http://studio.zerobrane.com/doc-luajit-debugging.html),
and [other Lua engines](http://studio.zerobrane.com/documentation.html#debugging).
* Live coding with Lua ([demo](http://notebook.kulchenko.com/zerobrane/live-coding-in-lua-bret-victor-style)),
Löve 2D ([demo](http://notebook.kulchenko.com/zerobrane/live-coding-with-love)),
Gideros ([demo](http://notebook.kulchenko.com/zerobrane/gideros-live-coding-with-zerobrane-studio-ide)),
Moai ([demo](http://notebook.kulchenko.com/zerobrane/live-coding-with-moai-and-zerobrane-studio)),
and Corona SDK ([demo](http://notebook.kulchenko.com/zerobrane/debugging-and-live-coding-with-corona-sdk-applications-and-zerobrane-studio)).
* Support for plugin-like components:
  - specs (`spec/`): file syntax, lexer, and keywords;
  - apis (`api/`): for code completion and tooltips;
  - interpreters (`interpreters/`): components for setting debugging and run-time project environment;
  - config (`cfg/`): contains style, color themes, and other settings;
  - packages (`packages/`): plugins that provide additional functionality;
  - tools (`tools/`): additional tools.

## Installation
=======
* Get Torch with the torch ezinstall script

<<<<<<< HEAD
```bash
curl -s https://raw.github.com/torch/ezinstall/master/install-all | bash
```
* Install mobdebug with torch-rocks with
=======
* A [short and simple overview](http://studio.zerobrane.com/doc-getting-started.html) for those who are new to this development environment.
* A list of [frequently asked questions](http://studio.zerobrane.com/doc-faq.html) about the IDE.
* [Tutorials and demos](http://studio.zerobrane.com/tutorials.html) that cover debugging and live coding for different environments.
* [Tips and tricks](http://studio.zerobrane.com/doc-tips-and-tricks.html).
>>>>>>> bf1d5c617e3a3e890dfb86f5b496c9872f4bad99

```bash
$ torch-rocks install mobdebug
```

```bash
$ git clone https://github.com/soumith/zbs-torch.git
$ cd zbs-torch
$ sh zbstudio.sh
```

## Usage

To debug a torch file,

* Start zbs from the zbs-torch directory with the command

```bash
$ sh zbstudio.sh
```
* Start the debugger server from "Project->Start Debugger Server"

* Change the interpreter to Torch-7 "Project->Lua Interpreter->Torch-7" 

* Add the following line to the top of the file you are debugging

```lua
require('mobdebug').start()
```
For Example, this file
```lua
require 'image'
print('Wheres Waldo?')
a=image.rotate(image.lena(), 1.0)
image.display(a)
print('OK Bye')
```
becomes
```lua
require('mobdebug').start()
require 'image'
print('Wheres Waldo?')
a=image.rotate(image.lena(), 1.0)
image.display(a)
print('OK Bye')
```

* Run the file from the menu "Project->Run"
* You should see the debugger stop at the first line of the file, then you can set breakpoints, continue, step etc.

## Original Author

### ZeroBrane Studio and MobDebug

  **ZeroBrane LLC:** Paul Kulchenko (paul@kulchenko.com)
## License

See LICENSE file.
