Topics: [Accessibility](../../../_tags/accessibility.md)

<a id="read-documents-and-web-pages-using-the-screen-reader"></a>

# Read documents and web pages using the screen reader

You can use the following screen reader commands to browse web pages, read longer text documents and navigate tables.

To start the screen reader and learn its basic control, go to [Get started with the screen reader](../../../tutorial/get-started-with-the-screen-reader.md#get-started-with-the-screen-reader).

#### NOTE
Ubuntu Desktop might present some challenges when using the screen reader. If you experience difficulty, refer to [Improve screen reader usability](../../troubleshoot/improve-screen-reader-usability.md#improve-screen-reader-usability).

<a id="orca-read-documents-using-caret-mode"></a>

## Read documents using caret mode

In caret mode, also known as caret browsing or caret navigation, you navigate a document using the text cursor (caret). You move the cursor using the arrow keys. As you navigate within the text of the document, Orca presents your current location.

Enable caret navigation:

* Applications with text input, such as text editors and word processors, enable caret navigation by default. The caret is the text cursor that you use to enter text in the window.
* In many GNOME applications and in web browser such as Firefox and Chrome, you can enable caret navigation by pressing `F7`.
* For other applications, consult their documentation.

Read the document using caret navigation:

* Use `Left` and `Right` to move and read by character.
* Use `Ctrl+Left` and `Ctrl+Right` to move and read by word.
* Use `Up` and `Down` to move and read by line.
* Use `Shift` in combination with the previous commands to select and unselect text.

To read, spell, and obtain the Unicode value for the current text, refer to [Examine a window](navigate-the-screen-using-the-screen-reader.md#orca-examine-a-window).

## Read the entire document

Read the whole document from your cursor position to the end:

### Laptop layout

`CapsLock+;`

### Desktop layout

`Insert+;`

This is similar to the Say All command described in [Examine a window](navigate-the-screen-using-the-screen-reader.md#orca-examine-a-window). However, Say All reads the whole window including buttons and other interface elements, and it’s limited to the currently visible content with no hierarchy. In contrast, reading the entire document respects more complex structure on web pages.

## Examine text formatting

Let Orca speak the text attributes of the current object, such as the font, style, alignment, and other formatting associated with the given characters:

### Laptop layout

`CapsLock+F`

### Desktop layout

`Insert+F`

### Preferences

The number of text attributes is large. You can customize which text attributes Orca presents in speech, along with the order in which Orca lists them. Optionally, Orca can indicate text attributes in braille by “underlining” them as you navigate a document. Go to the Text Attributes page of the Orca preferences dialog to change these settings.

You can also customize text attribute presentation for each application that you use in the application-specific settings.

## Identify misspelled words

You can learn about spelling issues in several ways:

* When you examine text formatting, Orca also announces spelling issues as one of the text attributes:

  ### Laptop layout

  `CapsLock+F`

  ### Desktop layout

  `Insert+F`

  Orca recognizes the spelling issue by reading the underline formatting that applications use to mark errors.
* Enable key echo or word echo. When you misspell a word, Orca announces “misspelled” so that you can immediately go back and correct the error.
* When you move the caret into a word that’s misspelled, Orca announces the presence of the spelling error.
* Perform detailed Where Am I to learn more details about the spelling issue:

  ### Laptop layout

  `CapsLock` + double-press `Enter`

  ### Desktop layout

  `Insert` + double-press `Enter`

<a id="orca-navigate-the-document-structure"></a>

## Navigate the document structure

The Structural Navigation feature enables you to browse elements in a document. The types of elements by which you can navigate include:

* Headings and other text blocks
* Form controls
* Links
* Lists and list items
* Landmarks, separators and anchors
* Tables and table cells

Structural Navigation is available in the following environments:

* On **web pages**, you can navigate the full range of elements.
* In **LibreOffice Writer** and OpenOffice Writer, you can navigate table cells.

### Navigate a web page

On web pages, you usually read the content without editing it. You can use the Structural Navigation commands directly. Refer to [Orca Structural Navigation commands](../../../reference/accessibility/orca-structural-navigation-commands.md#orca-structural-navigation-commands).

### Navigate elements in a text editor

In editable documents, such as those in **LibreOffice Writer** or an **online text editor**, pressing letters on the keyboard types text in the editor. Enable Structural Navigation to use letters as navigation shortcuts instead:

### Laptop layout

`CapsLock+Z`

### Desktop layout

`Insert+Z`

Browse elements using Structural Navigation commands:

* On web pages, refer to [Orca Structural Navigation commands](../../../reference/accessibility/orca-structural-navigation-commands.md#orca-structural-navigation-commands).
* In Writer, you can only use the commands for [Tables](../../../reference/accessibility/orca-structural-navigation-commands.md#orca-structural-navigation-commands-tables).

To go back to writing, disable Structural Navigation using the same shortcut that enables it.

## Read tables

Orca provides several features to access tables on web pages and in other documents.

### Read the cell or the row

Consider the list of **messages in your Inbox**. To hear the sender, subject, date and presence of attachments, you want Orca to **speak the row**.

On the other hand, consider the **rows in a spreadsheet**. You might not want to hear the full row because of the large number of cells in each row. In that case, you want Orca to only **speak the cell with focus**. Similar situations occur in document tables.

You can switch between cell and row reading for the current table:

### Laptop layout

`CapsLock+F11`

### Desktop layout

`Insert+F11`

You can customize whether Orca reads the cell or the full row by default. You can also choose different table reading modes for each type of table and for specific applications. To edit the options, go to the Speech page of Orca preferences.

### Structural Navigation

With Structural Navigation commands, you can locate tables, jump to the first or last cell and move to the next cell in any direction.

As you navigate the table, Orca announces the details about your position, such as the dimensions of the table or that you have reached the edge of the table.

For details, refer to [Navigate the document structure](#orca-navigate-the-document-structure).

### Mark a row or column as a header

Many tables have incorrectly marked headers. A row or column often serves as a header but it only uses bold or large text instead of semantic markup. In other cases, the header might be correct but the application or the toolkit don’t provide the information to the screen reader.

In those cases, you can manually mark a row or column as a header using the Dynamic Header feature.

#### Set a row as a header

Tell Orca that the current row is the one with the headers:

### Laptop layout

`CapsLock+R`

### Desktop layout

`Insert+R`

#### Set a column as a header

Tell Orca that the current column is the one with the headers:

### Laptop layout

`CapsLock+C`

### Desktop layout

`Insert+C`

#### Reset the custom header

To clear headers, double-press the command that you used to set them. This removes all custom row headers or column headers.

## Fill out forms

In browse mode, you can read forms. In focus mode, you can fill out form fields.

### Read or write

* Switch between the modes:

  ### Laptop layout

  `CapsLock+A`

  ### Desktop layout

  `Insert+A`
* To enable **sticky focus mode**, double-press the shortcut.
* To enable **sticky browse mode**, triple-press the shortcut.

### Browse form fields

In **browse** and **focus mode**, you can browse all focusable objects using `Tab` and `Shift+Tab`. After the last form field, you exit the form.

In **browse mode**, you can also use the following navigation:

* To navigate to a specific form field, use Structural Navigation commands for [Forms](../../../reference/accessibility/orca-structural-navigation-commands.md#orca-structural-navigation-commands-forms).
* To leave the form and navigate to another object, use [Orca Structural Navigation commands](../../../reference/accessibility/orca-structural-navigation-commands.md#orca-structural-navigation-commands).
* In certain forms and applications, you can use [caret mode](#orca-read-documents-using-caret-mode).

## Read live regions

A live region is a dynamically-updated portion of a web page, such as a table of sports statistics, a list of current stock prices, a log from a chat, or an alert displayed by the page you are reading.

Live regions are common on the web. However, not many web pages with live regions are fully accessible.

### Browse live regions

* Monitor live regions:

  ### Laptop layout

  `CapsLock+Shift+\`

  ### Desktop layout

  `Insert+Shift+\`
* Go to the next live region: `D`
* Go to the previous live region: `Shift+D`
* Go to last live region that made an announcement: `Y`
* Review the last **nine** announcements:

  ### Laptop layout

  `CapsLock` + `F1` through `F9`

  ### Desktop layout

  `Insert` + `F1` through `F9`

### Adjust live region politeness

Live regions have a “politeness” level. It tells your screen reader how important the information is and when you should hear the updates in that region.

In increasing order of importance, the politeness levels are:

1. Off
2. Polite
3. Assertive
4. Rude

You might not agree with the politeness level that the page author specified. In that case, you can modify the politeness level of live regions on the page:

* Cycle between politeness levels: `\`
* Set the default politeness level to *off*: `Shift+\`
