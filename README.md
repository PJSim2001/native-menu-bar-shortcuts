# Native Menu Bar Shortcuts

### Only macOS has been done so far! I'll attempt Windows later.

Edits I've made to [thomashope's native-menu-bar](https://github.com/thomashope/native-menu-bar) which adds shortcuts. Only the .c and .h have been modified. Feel free to integrate my changes into the main project! This is my first time forking something (and programming in Objective-C...).

## Changes

+ Added a ``char* shortcut`` parameter to:
  + ``nmb_appendMenuItem``
  + ``nmb_insertMenuItem``
  + ``nmb_appendCheckMenuItem``
  + ``nmb_insertCheckMenuItem``
  
  You can set it blank by just passing "". I figured I'd edit the original functions rather than just add the below ones since from the software I've seen, most developers want to put a majority of their menu bar items as having shortcuts.

+ Created function ``void nmb_setMenuItemShortcut(nmb_Handle menuItem, const char* shortcut)``, which lets you change the shortcut of a menu item after its creation.

+ Created function ``void nmb_setMenuItemShortcutSpecial(nmb_Handle menuItem, bool ret, bool enter, bool bkspce, bool del)`` which allows you to set the shortcuts to special control keys.
  
+ Created function ``void nmb_setMenuItemModifiers(nmb_Handle menuItem, bool ctrl, bool opt, bool cmd, bool shift)`` which allows you to set custom modifier keys.

## Notes

The new functions were placed after ``nmb_insertCheckMenuItem`` and before ``nmb_appendSeparator``. They've been properly documented in the header and commented on in the source, so please check those if you have any questions - they explain some of my design decisions and weird behavior I encountered which lead to some options being missing.

As stated in the intro, this is my first time using Objective-C, and just for context, I'm using this library for an SDL3 (C) project. Everything's working, but still consider this code amateurish (or maybe I'm underrating myself?).
