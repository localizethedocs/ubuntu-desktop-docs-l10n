Topics: [Accessibility](../../../_tags/accessibility.md)

<a id="navigate-the-screen-using-the-screen-reader"></a>

# Navigate the screen using the screen reader

You can use the following screen reader commands to identify windows, interact with interface elements and read text in applications.

To start the screen reader and learn its basic control, go to [Get started with the screen reader](../../../tutorial/get-started-with-the-screen-reader.md#get-started-with-the-screen-reader).

#### NOTE
Ubuntu Desktop might present some challenges when using the screen reader. If you experience difficulty, refer to [Improve screen reader usability](../../troubleshoot/improve-screen-reader-usability.md#improve-screen-reader-usability).

## Where am I?

Orca provides context-sensitive commands that describe the active window and the active object on the screen.

### Window information

Find out which window is active.

* Present the title bar:

  ### Laptop layout

  `CapsLock+/`

  ### Desktop layout

  `Insert+Enter` on the numeric keypad
* Present the status bar:

  ### Laptop layout

  `CapsLock` + double-press `/`

  ### Desktop layout

  `Insert` + double-press `Enter` on the numeric keypad

### Basic information

You can ask Orca for the *basic Where Am I* with any object on the screen. For most widgets, Orca at least tells you the label or name, the type or role of the widget, and the mnemonic or accelerator key if they exist.

For example, in tables, basic Where Am I gives you details about the table cell that you are in. In text, it presents the current line along with any text which is selected.

* Perform basic Where Am I:

  ### Laptop layout

  `CapsLock+Enter`

  ### Desktop layout

  `Insert+Enter`

### Detailed information

Only certain objects provide the *detailed Where Am I* information. These objects contain a lot of information that you may wish to know, but only on demand.

For example, if you are in the spell checker of an application where Orca provides enhanced support, the basic Where Am I repeats the spelling error. The detailed Where Am I presents the full details of the error. The detailed Where Am I also tells you the position in a progress bar, the status of check boxes and radio buttons, the children in a tree object, the type of a link or the cell coordinates in a table.

* Perform detailed Where Am I:

  ### Laptop layout

  `CapsLock` + double-press `Enter`

  ### Desktop layout

  `Insert` + double-press `Enter`

<a id="orca-examine-a-window"></a>

## Examine a window

With the **Flat Review** feature, you can review the text and widgets of the active window. In this mode, Orca treats the window as a two-dimensional sheet of text. It browses the objects in the foreground, ignoring widget hierarchy or other logical grouping within the window. It can’t access window elements that are currently off-screen.

You can navigate the “flattened” content by line, by word, by character, and by object.

When you enter Flat Review mode, it captures the state of the window at that moment. If the content of the window changes, Flat Review doesn’t update automatically. You can refresh the Flat Review context by toggling Flat Review off and back on.

If you use the application’s navigation commands to move the caret or to give focus to another object, you automatically leave Flat Review.

* Toggle Flat Review (refreshes the window content):

  ### Laptop layout

  `CapsLock+P`

  ### Desktop layout

  `Insert+-` on the numeric keypad
* Review the current item or widget:

  ### Laptop layout

  `CapsLock+Ctrl+K`

  ### Desktop layout

  `Insert+5` on the numeric keypad
* Use Say All to review the current dialog or window:

  ### Laptop layout

  `CapsLock` + double-press `;`

  ### Desktop layout

  Double-press `+` on the numeric keypad

### Review the window by line

* First line (the “home” position):

  ### Laptop layout

  `CapsLock+Ctrl+U`

  ### Desktop layout

  `Insert+7` on the numeric keypad
* Previous line:

  ### Laptop layout

  `CapsLock+U`

  ### Desktop layout

  `7` on the numeric keypad
* Current line:

  ### Laptop layout

  `CapsLock+I`

  ### Desktop layout

  `8` on the numeric keypad
* Spell current line:

  ### Laptop layout

  `CapsLock` + double-press `I`

  ### Desktop layout

  Double-press `8` on the numeric keypad
* Phonetically spell current line:

  ### Laptop layout

  `CapsLock` + triple-press `I`

  ### Desktop layout

  Triple-press `8` on the numeric keypad
* Next line:

  ### Laptop layout

  `CapsLock+O`

  ### Desktop layout

  `9` on the numeric keypad
* Last line (the “end” position):

  ### Laptop layout

  `CapsLock+Ctrl+O`

  ### Desktop layout

  `Insert+9` on the numeric keypad

### Review the window by word

* Word above:

  ### Laptop layout

  `CapsLock+Ctrl+J`

  ### Desktop layout

  `Insert+4` on the numeric keypad
* Previous word:

  ### Laptop layout

  `CapsLock+J`

  ### Desktop layout

  `4` on the numeric keypad
* Current word:

  ### Laptop layout

  `CapsLock+K`

  ### Desktop layout

  `5` on the numeric keypad
* Spell current word:

  ### Laptop layout

  `CapsLock` + double-press `K`

  ### Desktop layout

  Double-press `5` on the numeric keypad
* Phonetically spell current word:

  ### Laptop layout

  `CapsLock` + triple-press `K`

  ### Desktop layout

  Triple-press `5` on the numeric keypad
* Next word:

  ### Laptop layout

  `CapsLock+L`

  ### Desktop layout

  `6` on the numeric keypad
* Word below:

  ### Laptop layout

  `CapsLock+Ctrl+L`

  ### Desktop layout

  `Insert+6` on the numeric keypad

### Review the window by character

* Previous character:

  ### Laptop layout

  `CapsLock+M`

  ### Desktop layout

  `1` on the numeric keypad
* Current character:

  ### Laptop layout

  `CapsLock+,`

  ### Desktop layout

  `2` on the numeric keypad
* Phonetically speak current character:

  ### Laptop layout

  `CapsLock` + double-press `,`

  ### Desktop layout

  Double-press `2` on the numeric keypad
* Speak the Unicode value of the current character:

  ### Laptop layout

  `CapsLock` + triple-press `,`

  ### Desktop layout

  Triple-press `2` on the numeric keypad
* Next character:

  ### Laptop layout

  `CapsLock+.`

  ### Desktop layout

  `3` on the numeric keypad
* Last character on the current line:

  ### Laptop layout

  `CapsLock+Ctrl+M`

  ### Desktop layout

  `Insert+1` on the numeric keypad

## Find objects in a window

You can use Orca’s Find feature to quickly locate objects that are visible on-screen within the current window.

Orca Find is based on the [Flat Review](#orca-examine-a-window) feature.

1. Open the Orca Find dialog:

   ### Laptop layout

   `CapsLock+[`

   ### Desktop layout

   `Delete` on the numeric keypad
2. A dialog box opens. Enter the search term.

   You can specify several options such as case sensitivity, where the search starts or whether it wraps around the end of the document back to the start.
3. When the search finds a match, Flat Review automatically activates and the matching item or text becomes the current review item.

   Note that the search doesn’t modify the focus within the application and it doesn’t reposition the caret. If you need to accomplish either, please see Orca’s Mouse/Pointer-Related Commands.
4. You can quickly search for the next or previous match:
   * Move flat review to the next instance of a string:

     ### Laptop layout

     `CapsLock+]`

     ### Desktop layout

     `Insert+Delete` on the numeric keypad
   * Move flat review to the previous instance of a string:

     ### Laptop layout

     `CapsLock+Ctrl+]`

     ### Desktop layout

     `Insert+Shift+Delete` on the numeric keypad

<!--
This feature doesn't work at all and leaves Orca in a stuck, unusable state. Commenting out for now.

Mouse commands don't work either but at least they don't permanently disable Orca:
https://help.gnome.org/users/orca/stable/commands_mouse.html.en

(orca-mouse-review)=
## What's under the mouse cursor?

With the Mouse Review feature, Orca identifies the object that's visually under the cursor as you move the mouse. If you move the cursor over an accessible object with information to present, Orca presents that object and its information to you. Mouse Review isn't limited to the active window.

Mouse Review is disabled by default because it processes all the changes in the position of the cursor.

\* You can enable it permanently:

    Enable the {guilabel}\`Speak object under mouse\` checkbox on the {guilabel}\`General\` page of Orca's Preferences dialog.

\* You can also set a keyboard shortcut to enable Mouse Review for a short time:

    On the {guilabel}\`Key Bindings\` page of Orca Preferences, bind the command named {guilabel}\`Toggle mouse review mode\` to a keyboard shortcut. Then you can enable and disable Mouse Review on an as-needed basis.

:::{note}
You can choose to have Mouse Review always enabled or not and still toggle it on and off by binding and using the Toggle mouse review mode command. It is not necessary to enable it in order to toggle it because settings and keybindings are independent of one another.
:::
-->

## Bookmark an object for later

You can indicate that an object on the screen is of interest and return to it later.

Orca provides several commands which can be used to “bookmark” a given object for the purpose of navigating back to it later.

### Save a bookmark

You can set up to six bookmarks per environment. These can be objects such as widgets within an application or objects on a web page. You can also save bookmarks so that they persist between Orca sessions.

* Save a bookmark to the numbered slot:

  ### Laptop layout

  `CapsLock+Alt` + a number from `1` to `6`

  ### Desktop layout

  `Insert+Alt` + a number from `1` to `6`
* Save the defined bookmarks for the application or page:

  ### Laptop layout

  `CapsLock+Alt+B`

  ### Desktop layout

  `Insert+Alt+B`

### Return to a bookmark

You can navigate to the bookmark later, even if you haven’t permanently saved the bookmarks associated with your current environment. You can find the bookmark based on its number, or you can browse the saved bookmarks just like Structural Navigation objects.

When you select a bookmark, the exact behavior depends on the current environment. If you are in web content, the caret moves to the bookmark so that you can continue reading. Otherwise, Flat Review activates and the bookmark becomes the current review item.

* Go to a specific, numbered bookmark:

  ### Laptop layout

  `CapsLock` + a number from `1` to `6`

  ### Desktop layout

  `Insert` + a number from `1` to `6`
* Go to the previous bookmark for the application or page:

  ### Laptop layout

  `CapsLock+Shift+B`

  ### Desktop layout

  `Insert+Shift+B`
* Go to the next bookmark for the application or page:

  ### Laptop layout

  `CapsLock+B`

  ### Desktop layout

  `Insert+B`

## Obtain the time and date

Say the current time:

### Laptop layout

`CapsLock+T`

### Desktop layout

`Insert+T`

Say today’s date:

### Laptop layout

`CapsLock` + double-press `T`

### Desktop layout

`Insert` + double-press `T`

## Read chat room messages

In IRC (Internet Relay Chat) clients and other supported chat applications, you can browse the latest messages:

### Laptop layout

`CapsLock` + `F1` through `F9`

### Desktop layout

`Insert` + `F1` through `F9`

## Keyboard navigation shortcuts

For keyboard shortcuts that launch applications, switch between desktop elements and navigate desktop menus, refer to [Navigate the interface using the keyboard](../navigate-the-interface-using-the-keyboard.md#navigate-the-interface-using-the-keyboard).
