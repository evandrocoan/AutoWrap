Auto (Hard) Wrap for Sublime Text 2/3
====================
[![Build Status](https://travis-ci.org/randy3k/AutoWrap.svg?branch=master)](https://travis-ci.org/randy3k/AutoWrap)
[![Coverage Status](https://coveralls.io/repos/github/randy3k/AutoWrap/badge.svg?branch=master)](https://coveralls.io/github/randy3k/AutoWrap?branch=master)
<a href="https://packagecontrol.io/packages/AutoWrap"><img src="https://packagecontrol.herokuapp.com/downloads/AutoWrap.svg"></a>
<a href="https://www.paypal.me/randy3k/5usd" title="Donate to this project using Paypal"><img src="https://img.shields.io/badge/paypal-donate-blue.svg" /></a>
<a href="https://liberapay.com/randy3k/donate"><img src="http://img.shields.io/liberapay/receives/randy3k.svg?logo=liberapay"></a>

Automatic hard wrap beyond wrap width. It could be useful for text documents. [Sublime-Wrap-Plus](https://github.com/ehuss/Sublime-Wrap-Plus) could be used together with AutoWrap for the best experience.

![](https://raw.githubusercontent.com/randy3k/AutoWrap/master/demo.gif)


## Installation

### By Package Control

1. Download & Install **`Sublime Text 3`** (https://www.sublimetext.com/3)
1. Go to the menu **`Tools -> Install Package Control`**, then,
    wait few seconds until the installation finishes up
1. Now,
    Go to the menu **`Preferences -> Package Control`**
1. Type **`Add Channel`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    input the following address and press <kbd>Enter</kbd>
    ```
    https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json
    ```
1. Go to the menu **`Tools -> Command Palette...
    (Ctrl+Shift+P)`**
1. Type **`Preferences:
    Package Control Settings – User`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    find the following setting on your **`Package Control.sublime-settings`** file:
    ```js
    "channels":
    [
        "https://packagecontrol.io/channel_v3.json",
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
    ],
    ```
1. And,
    change it to the following, i.e.,
    put the **`https://raw.githubusercontent...`** line as first:
    ```js
    "channels":
    [
        "https://raw.githubusercontent.com/evandrocoan/StudioChannel/master/channel.json",
        "https://packagecontrol.io/channel_v3.json",
    ],
    ```
    * The **`https://raw.githubusercontent...`** line must to be added before the **`https://packagecontrol.io...`** one, otherwise,
      you will not install this forked version of the package,
      but the original available on the Package Control default channel **`https://packagecontrol.io...`**
1. Now,
    go to the menu **`Preferences -> Package Control`**
1. Type **`Install Package`** on the opened quick panel and press <kbd>Enter</kbd>
1. Then,
    search for **`AutoWrap`** and press <kbd>Enter</kbd>

See also:

1. [ITE - Integrated Toolset Environment](https://github.com/evandrocoan/ITE)
1. [Package control docs](https://packagecontrol.io/docs/usage) for details.


### Usage

#### To toggle Auto Wrap
Type `Auto Wrap` in command palette or Go to menu `Edit -> Auto Wrap`.

#### Control wrap width

Wrap width is detected in the following order

1. `auto_wrap_width`
2. `wrap_width`
3. `rulers`
4. default 80

### Settings

#### To activate Auto Wrap for a specific syntax at start up

Put the following in your syntax specific preference.<br>
Menu -> Preference -> Settings - More -> Syntax Specific - User

    {
        "auto_wrap" : true
    }

#### You can also change `auto_wrap_width` by

    {
        "auto_wrap_width" : 100
    }

#### Long words

In default, long word will break into a new line.
To disable this behavior, consider

    {
        "auto_wrap_break_long_word" : false
    }

#### Break beyond wrap width only

If true, long sentence will break only if the cursor is beyond wrap width.

    {
        "auto_wrap_beyond_only" : true
    }

#### Break patterns

Upon typing, AutoWrap searches for these characters (in regex, to be concatenate by `|`) and a line would break at (right before) a matched location. Note that Backslash has to be double escaped.

    {
        # it is the default
        "auto_wrap_break_patterns" :  ["\\[", "\\(", "\\{", " ", "\\n"]
    }
