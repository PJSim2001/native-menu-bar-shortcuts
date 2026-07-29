# Native Menu Bar, with Shortcut Support

### ⚠️ Only macOS has been done so far! I'll attempt Windows later. ⚠️

Edits I've made to [thomashope's native-menu-bar](https://github.com/thomashope/native-menu-bar) which allow you to assign shortcuts to your entries. Only the .c and .h files have been modified. Feel free to integrate my changes into the main project!

## Changes

+ Added a ``char* shortcut`` parameter to:
  + ``nmb_appendMenuItem``
  + ``nmb_insertMenuItem``
  + ``nmb_appendCheckMenuItem``
  + ``nmb_insertCheckMenuItem``
  
  You can set it blank by just passing "".

+ Created function ``void nmb_setMenuItemShortcut(nmb_Handle menuItem, const char* shortcut)``, which lets you change the shortcut of a menu item after its creation to a standard key.

+ Created function ``void nmb_setMenuItemShortcutFunctionKey(nmb_Handle menuItem, const int num)``, which lets you set the shortcut of a menu item to a function key from F1-F19.

+ Created function ``void nmb_setMenuItemShortcutSpecial(nmb_Handle menuItem, bool ret, bool enter, bool backspace, bool del)`` which allows you to set a shortcut to one of the special control keys.
  
+ Created function ``void nmb_setMenuItemModifiers(nmb_Handle menuItem, bool ctrl, bool opt, bool cmd, bool shift)`` which allows you to set custom modifier keys.

## Notes

The new functions were placed after ``nmb_insertCheckMenuItem`` and before ``nmb_appendSeparator``. They've been properly documented in the header and commented on in the source, so please check those if you have any questions - they explain some of my design decisions and the behavior I encountered which lead to some options being missing.

This was my first time programming something in Objective-C (for context, I created this branch for use in an SDL3 (C) project). While everything works, it's possible that it's not as efficient as it could be.
