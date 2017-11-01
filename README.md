SublimeCodeIntel
================

This Code Intelligence plugin for [Sublime Text](https://www.sublimetext.com)
provides an interface to [CodeIntel](http://pypi.python.org/pypi/CodeIntel).
CodeIntel is a code intelligence engine that was ported from
[Open Komodo Editor](http://www.openkomodo.com) to a stand-alone Python package.

CodeIntel supports all the languages Komodo Editor supports for Code Intelligence
(CIX, CodeIntel2) and a few others:

> ActionScript, Django, Docker, EJS, epMojo, HTML, KomodoSnippet,
> LaravelBlade, Mason, Mustache, MXML, PHP, R, reStructuredText, RHTML,
> Smarty, TracWiki, TemplateToolkit, Twig, XBL, XML, XSLT, XUL, Python,
> Python3, Ruby, Perl, Go, ECMAScript, JavaScript, Node.js, CSS, SCSS, Sass,
> Less, HTML5, Tcl, C/C++, Objective-C.

The plugin provides the following features:

-   Jump to Symbol Definition - Jump to the file and line of the
    definition of a symbol.
-   Imports autocomplete - Shows autocomplete with the available
    modules/symbols in real time.
-   Function Call tooltips - Displays information in the status bar
    about the working function.

The package should work in all three platforms (MacOS X, Windows and Linux).

[![Click here to lend your support to CodeIntel/SublimeCodeIntel and make a donation!](https://www.paypalobjects.com/en_GB/i/btn/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VVX4Q9H3924LE)

CodeIntel Installation
----------------------

Before installing `SublimeCodeIntel`, you must ensure that `CodeIntel` is installed
on your system. To install `CodeIntel`, do the following:

1. Install [Python](http://python.org) and [pip](http://www.pip-installer.org/en/latest/installing.html) (Python 3 requires pip3).

1. Install `CodeIntel` by typing the following in a terminal:
   ```
   # For Python 2
   [sudo] pip install --upgrade --pre CodeIntel

   # For Python 3
   [sudo] pip3 install --upgrade --pre CodeIntel
   ```

**Note:** `SublimeCodeIntel` requires `CodeIntel` 2.0 or later.

Plugin Installation
-------------------

**With the Package Control plugin:** The easiest way to install
`SublimeCodeIntel` is through Package Control, which can be found at
this site: <http://wbond.net/sublime_packages/package_control>

Once you install Package Control, restart Sublime Text and bring up the
Command Palette (`Command+Shift+P` on OS X, `Control+Shift+P` on
Linux/Windows). Select "Package Control: Install Package", wait while
Package Control fetches the latest package list, then select
SublimeCodeIntel when the list appears. The advantage of using this
method is that Package Control will automatically keep SublimeCodeIntel
up to date with the latest version.

\*\*Without <Git:**> Download the latest source from
[GitHub](http://github.com/SublimeCodeIntel/SublimeCodeIntel) and copy
the whole directory into the Packages directory.

\*\*With <Git:**> Clone the repository in your Sublime Text Packages
directory, located somewhere in user's "Home" directory:

    git clone git://github.com/SublimeCodeIntel/SublimeCodeIntel.git

The "Packages" packages directory is located differently in different
platforms. To access the directory use:

-   OS X:

        Sublime Text -> Preferences -> Browse Packages...

-   Linux:

        Preferences -> Browse Packages...

-   Windows:

        Preferences -> Browse Packages...

Using
-----

-   Start typing code as usual, autocomplete will pop up whenever it's
    available. SublimeCodeIntel will also allow you to jump around
    symbol definitions even across files with just a click ..and back.

    For Mac OS X:

    :   -   Jump to definition = `Control+Click`
        -   Jump to definition = `Control+Command+Alt+Up`
        -   Go back = `Control+Command+Alt+Left`
        -   Manual Code Intelligence = `Control+Shift+space`

    For Linux:

    :   -   Jump to definition = `Super+Click`
        -   Jump to definition = `Control+Super+Alt+Up`
        -   Go back = `Control+Super+Alt+Left`
        -   Manual Code Intelligence = `Control+Shift+space`

    For Windows:

    :   -   Jump to definition = `Alt+Click`
        -   Jump to definition = `Control+Windows+Alt+Up`
        -   Go back = `Control+Windows+Alt+Left`
        -   Manual Code Intelligence = `Control+Shift+space`

Don't despair! The first time you use it it needs to build some indexes
and it can take more than a few seconds.

It just works!

Configuring
-----------

For adding additional library paths (django and extra libs paths for
Python or extra paths to look for .js files for JavaScript for example),
either add those paths as folders to your Sublime Text project, or
modify SublimeCodeIntel User settings. User settings can be configured
in the User File Settings:

Do NOT edit the default SublimeCodeIntel settings. Your changes will be
lost when SublimeCodeIntel is updated. ALWAYS edit the user
SublimeCodeIntel settings by selecting "Preferences-&gt;Package
Settings-&gt;SublimeCodeIntel-&gt;Settings - User". Note that individual
settings you include in your user settings will **completely** replace
the corresponding default setting, so you must provide that setting in
its entirety.

Available settings:

-   A list of disabled languages can be set using
    "disabled\_languages". Ex.
    `"disabled_languages": ['css']`
-   Live autocomplete can be disabled by setting "live" to
    false.
-   Information for more settings is available in the
    `SublimeCodeIntel.sublime-settings` file in the package.

Troubleshooting
---------------

If you are having problems or SublimeCodeIntel seems
slow/unresponsive/non-working, there are some things you should try:

1.  Make sure the SublimeCodeIntel is not being treated as an ignored
    package.
2.  Regenerate indexing database.
3.  Open a new issue.

### Ignored package?

To make sure Sublime Text didn't add SublimeCodeIntel to the list of
ignored packages (this happens some times when packages are being
installed/upgraded):

-   Select the `Preferences/Settings - Default` menu item
-   Find the `ignored_packages` setting and remove SublimeCodeIntel from
    the list.

### Regenerate index

To force re-indexation of the code intelligence database you need to
follow these steps:

-   Close Sublime Text
-   Open a terminal or navigate through your directories to find the
    directory `~/.codeintel` that contains `codeintel.log`, `VERSION`
    and the directory `db`. In Windows, this should be at
    `%userprofile%\.codeintel`.
-   Delete the whole directory `~/.codeintel` and all of its content.
    Particularly, if you want to delete only the indexes, the code
    intelligence database indexes are located inside `~/.codeintel/db`.
-   Start Sublime Text
-   Try doing some code intelligence with the files in your project and
    enjoy a clean re-indexing! (Remember that the database is being
    regenerated with this procedure, so you'll see it takes some time to
    autocomplete the first few times, you'll have to wait a bit for
    things to be fast again)

### Opening an issue

If the problems persists after trying the above solutions, open a new
issue in <https://github.com/SublimeCodeIntel/SublimeCodeIntel/issues/>

When opening new issues, please check no other issues exist which report
the same problem and provide all the messages from the Sublime Text
console (the console is accessed via the `ctrl+`\` shortcut or the
`View > Show Console` menu) and the `~/.codeintel/codeintel.log` file
(`%userprofile%\.codeintel\codeintel.log` in Windows) as well as
mentioning the Sublime Text version, the platform you are using and the
languages you are using the code intelligence on.


What's New
----------

v3.0.0 (unreleased, beta):

-   Uses CodeIntel as an OOP command and package. Needs to install
    CodeIntel with pip: pip install --upgrade --pre CodeIntel

v2.2.0 (2015-03-26):

-   Fixed issue with tabs and autocomplete

v2.1.9 (2015-03-21):

-   Fixed issue with codeintel\_enabled()

v2.1.8 (2015-03-18):

-   Fixed issue with is\_enabled()
-   Do not autocomplete on ENTER

v2.1.7 (2015-01-26):

-   Fixed triggering issues with autocompletion and stop chars.
-   ST2 improvements. Still might show "slow plugin" (just ignore,
    project\_file\_name is being emulated from ST3, which is "slow")
-   Cleanups

v2.1.6 (2015-01-23):

-   Optimizations.
-   Compatibility issues with ST2.
-   Stop characters fixed.

v2.1.5 (2015-01-22):

-   Cleanups.
-   Autocomplete also triggered after space (for import&lt;space&gt;
    autocompletions).
-   Tooltip and snippets for functions re-added.

v2.1.4 (2015-01-21):

-   Improved compatibility with ST2
-   PHP magic-methods tweaks ported from wizza-smile's fork.

v2.1.3 (2015-01-20):

-   Features and enhancements from wizza-smile's fork.
-   PHP completions within function brackets.

v2.1.2 (2015-01-16):

-   Fixed issue with ordereddict in ST3 (Python 3).
-   Fixed issue with unrevised languages.
-   Perl compatibility improved/fixed.

v2.1.1 (2015-01-14):

-   Currently, this version features all the new great enhancements by
    [wizza-smile](https://github.com/wizza-smile) which he is currently
    working on, in his own fork of SublimeCodeIntel: SublimeCodeIntel3
    at <https://github.com/wizza-smile/SublimeCodeIntel3>
-   Sublime Text 2 compatibility fixed.
-   Fix the "codeintel\_scan\_exclude\_dir" setting (it was doing
    nothing at all so far!).

v2.1.0 (2015-01-13):

-   New settings concept. Settings can now be defined in
    \*.sublime-project file.
-   Define the directory, where your projects codeintel database should
    reside (new setting "codeintel\_database\_dir").
-   Sublime style word completions from buffer (new setting
    "codeintel\_word\_completions" possible values: "buffer", "all" or
    "none").
-   Completions are now showing user-defined snippets.
-   PHP local variables support.
-   PHP static variables support.
-   PHP completions from HTML embedded blocks.
-   Improved speed for PHP completions dramatically by fixing the number
    of import libs.

v2.0.6 (2013-09-21):

-   Tooltips can use Popups, Output Panel or Status Bar ("popup",
    "panel", "status" respectively, in the settings)
-   Resolved issues with XML and other languages.
-   Improved speed by using cache for some things (added
    zope.cachedescriptors)

v2.0.5 (18-09-2013):

-   Resolved issues with ST2 in Mac OS X and Windows
-   Fixed a few problems with Ruby and HTML parsers in ST3

v2.0.4 (16-09-2013):

-   First non-pre-release for ST3

v2.0.3 (14-09-2013):

-   Libraries built for compatibility with more systems.

v2.0.2 (12-09-2013):

-   Initial Sublime Text 3 support!
-   OpenKomodo codebase updated to r13636
-   Snippets insertion delayed a bit.
-   Tooltips are removed when line changes.
-   Improved autocomplete in HTML.

v2.0.1 (19-07-2013):

-   Removed some Linux dependencies to GLIBC\_2.4.
-   Sublime Text 2 built-in auto complete no longer disabled by default
    (use "sublime\_auto\_complete": false setting instad).

v2.0 (11-07-2013):

-   SublimeCodeIntel's openkomodo codeintel engine updated. The new
    codeintel is faster and more reliable.
-   Sources have their own repositories at
    <http://github.com/SublimeCodeIntel>
-   Disables Sublime Text 2's auto\_complete by default (new
    `sublime_auto_complete` setting)
-   JavaScript and PHP: Do not include all files and directories from
    the project base directory while scanning.
-   JavaScript: Maximum directory depth is set to 2 (add explicit paths
    using javascriptExtraPaths).
-   PHP: Maximum directory depth is set to 5 (add explicit paths using
    phpExtraPaths).
-   Snippets for functions inserted during autocomplete.
-   Binary files for Linux, Windows and Mac OS X updated.
-   Shortcuts for jump to definition have changed.
-   PHP and UDL languages bugs fixed.
-   Stability improved (Should no longer use 100% CPU all the time.)

v1.4 (05-07-2013):

-   Added improved Package Control support and updated old versions.
-   Started transition to v2.0

v1.3 (20-12-2011):

-   This build should fix many of the problems seen in Linux systems.
-   Libraries for Linux rebuilt with libpcre statically (libpcre bundled
    for Linux builds).
-   `calltip()` is now thread safe (which caused some strange behavior
    in Linux where Sublime Text 2 ended up being unresponsive).

v1.2 (18-12-2011):

-   Added palette commands to disable/enable the plugin in many ways.
-   Added `codeintel_live_disabled_languages` and fixed `codeintel_live`
    to disable SublimeCodeIntel live autocomplete mode.
-   Support for new completion settings in Sublime Text 2 Build 2148.
-   JavaScript support improved (it's now much nicer with the CPU).
-   CSS files support much improved (thanks to Jon's new features in
    autocomplete).
-   Smarter language detection and fallbacks.
-   Improved autocomplete triggering, should now respond better.

License
-------

The plugin is based in code from the Open Komodo Editor and has a MPL license.

Ported from Open Komodo by German M. Bravo (Kronuz).
