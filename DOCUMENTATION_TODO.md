# Principal Enhancements


# Screenman Enhancements
## Use of Mouse in Screenman Forms (DONE)
To use your mouse with Screenman forms, your terminal emulator needs to be able
to receive ANSI standard control sequences to turn the mouse on and off. Set up
your terminal emulator so that the keyboard emulation is in “VT100+ mode.” Once
you are in a Screenman form, click the mouse at the command line or any of the
fields in the form.
http://www.hardhats.org/fileman/u1/sm_intro.htm#Screen

If you do not want Screenman to recognize mouse clicks, use the Kernel
parameter (created by running ^DINIT) that is named “DI SCREENMAN NO MOUSE”.
http://www.hardhats.org/fileman/pm/sm_intro.htm

## Record Selection as a Full Screenman Page (DONE)
The Screenman Record Selection page can now be a full Screenman page using a
computed multiple pointer, so that the user can select an entry by scrolling up
or down. This new feature lets forms contain embedded lookups.
You can set this up automatically when you create a form. At the query “Do you
want your Form to begin with a display of all entries, for selection,” answer
“Yes.” The initial position can be set to be the user’s last selection, rather
than first, last, or new.
http://www.hardhats.org/fileman/pm/fe_invok.htm

## Expanded Multiples (DONE)
Multiples within a single Screenman page can now be more than one line deep.
http://www.hardhats.org/fileman/pm/sf_repbl.htm

## Custom Colors Option
The “Customize Colors” suboption within Screenman allows selection of ANSI
colors for all Screenman presentations, on a parameterized basis (user,
institution, etc.) using Kernel parameters.
http://www.hardhats.org/fileman/u1/sm_intro.htm

## Quick Exit from Word Processing Pages
Editing a Screenman word­processing page ends with two empty lines, so that
"F1­E" is not required to leave the page.
http://www.hardhats.org/fileman/u1/se_intro.htm#Exiting_Saving

## Indication of Word-processing Data
A + now indicates in a Screenman form whether a word­processing field already
contains data. http://www.hardhats.org/fileman/u1/sm_intro.htm#Wp

## Screen Print
“F1­P” allows printing of the screen (including all multiples).
http://www.hardhats.org/fileman/u1/sm_intro.htm#Fields
http://www.hardhats.org/fileman/u1/sm_intro.htm#Multiples

# Internationalization
## Fileman is Translation-ready
All hard­coded display strings in File Manager have been converted to the
Fileman Dialog framework, so translation can be table­driven.

## New Entries in Dialog File (.84)
Many new entries have been added to the Dialog file to handle all end­user
interactions.

## Many New Languages in File .85
The Language File (.85) can now be extended by running it to include all ISO
639 standard languages.
http://www.hardhats.org/fileman/pm/app_b_l.htm

## New Dialog Framework for Data Dictionary Elements
File names, field labels, set values, and help messages can be entered into the
^DD schema for any of the languages listed in File .85.
http://www.hardhats.org/fileman/pm/app_b_l.htm

## New Entry Points to Help Translate DD Elements
New direct­mode tools have been created to help translate DD elements.
For example, to enter Spanish: DO SPANISH^DIALOGZ or DO LANG^DIALOGZ(3).

## Consistent Date Formatting
Formatting of date output is now consistently done throughout all the end­ user
routines. Changing the global node ^DD(“DD”) will change the way all Fileman
dates are output. Re­running ^DINIT will not change this node.
http://www.hardhats.org/fileman/pm/app_b_l.htm

## International Date Input
Fileman’s internationalization framework has been extended to improve support
for international dates. International date input (“I” parameter) allows alpha
dates and forms such as “2010131”, “20100131”, and “31 Jan 2010.”

## Upper/Lowercase Translations are Consistent
Fileman’s internationalization framework has been made consistently independent
of the ASCII character set, to improve support for international case
conversion.

## Two- and Three-letter Language Abbreviations
The Language file (.85) now can store two­and three­letter abbreviations for languages.
http://www.hardhats.org/fileman/pm/app_b_l.htm

# Data Analysis Tools
## Check all Pointers into a Given File
A fourth Data Dictionary utility (“find pointers into a file”) checks all files
with pointers into a given File. The utility gives 4 kinds of output (here
using Patient file (2) as an example):
```
1 One particular PATIENT Entry
2 All PATIENT Entries
3 Non-existent PATIENT Entries
4 Entries from a PATIENT Searc
```
http://www.hardhats.org/fileman/u2/fa_frm.htm

# Automatic Auditing
To improve version­control for data dictionaries, DD changes are always audited
(in File .6). There is no need to turn on DD auditing file­by­file.
http://www.hardhats.org/fileman/u2/au_dd.htm

## Showing Past Changes to Data Dictionary
The “Show Past Changes to DDs” auditing sub­option shows all DD changes since a
certain date.
http://www.hardhats.org/fileman/u2/au_dd.htm#Reviewing

## Showing Changes by a Specific User
“Monitor a User” is now the second auditing option. It shows every entry in an
audited file touched by a given user in an audited file.
http://www.hardhats.org/fileman/u2/au_dd.htm#Reviewing

# Modified Auditing Menu
The auditing menu has been modified to be better organized and more intuitive.
http://www.hardhats.org/fileman/u2/au_intro.htm

## Entry Access Audit
The entry point ACCESSED^DIET will record access to a file entry in the audit
file. Previously Fileman could only record audits for added, modified, or
deleted fields. Now it can record access to a specific entry in a file.
 http://www.hardhats.org/fileman/u2/au_intro.htm

# The Meta Data Dictionary
Run ^DDD during Fileman install to create the new Meta Data Dictionary file
(.9). The Meta Data Dictionary lists all fields in all files in a searchable
format.

# Improvements to the Verify Fields Utility
http://www.hardhats.org/fileman/u2/ut_ver.htm
## Verify Fields checks for duplicates and dangling pointers in cross-references.
## Verify Fields output has been made interruptible.

## New Verify Pointers Option
The Verify Fields option has been converted into a new Verify Data menu, which
contains Verify Fields and a new Verify Pointers option. Verify Pointers will
find and report dangling and badly defined pointers.

## Input and Output Transform mirroring
If a field’s contents fail the Input Transform, and an Output Transform exists
for the same field, then the Output Transform is applied to the field's
contents. If the result of applying the Output Transform to the field's
contents passes the Input Transform, then the field contents are deemed to be
valid.

## Index Limit Checks
Verify Fields checks that the index values do not exceed the thirty-character limit.

## Language support
If a user's language is set to a non-English language, and if a translation of
a field label exists for that language, then Verify Fields output displays the
translated field label.

## Bug fixes
A bug was fixed to suppress the accidental echo of dates in the Verify Fields output.

# Comparing Data and Data Dictionaries across Environments
## Namespace Compare
A new Transfer menu option, Namespace Compare, lets you identify differences in
data and DDs between different MUMPS environments, to help with version
control.

# Other Enhancements
## User Interface Changes
### Select Prompt: Extended Selection by IEN
Lookup enhancement: if the .01 field of the file being selected from is a
pointer to another file, you can use a double accent grave (``) to pick a
pointed­to entry by its IEN.

### Allow Terminal Emulators Deeper Than 24 Lines
Fileman now supports longer screens.

### Printing Multiples in Sorted Order
Until now, when printing sorted records, any subentries within those records
were displayed unsorted, in order by internal entry number. A new B print
specifier will ensure that subentries are displayed in order.
http://www.hardhats.org/fileman/u1/pr_intro.htm#print_qualifiers

### Enhanced Control of Input Templates
Within input templates, subfiles can now be edited in more than one place
within the template, so that different subfields can be edited each time.

## Fileman Browser Enhancements
Fileman will be optimistic and assume the terminal emulator supports the
browser, rather than consult the Kernel.
You can now quit the browser using CTRL­E.
You can now print the text being browsed using F1­F1­P.
http://www.hardhats.org/fileman/u1/br_intro.htm#command_keystroke

# API Changes
## Enhancements to FIND^DIC and LIST^DIC
Third argument (fields) can now be a computed expression, not just a field.
http://www.hardhats.org/fileman/pm/db_dic_l.htm
http://www.hardhats.org/fileman/pm/db_dicf.htm

New E flag returns the complete list of matches even if errors are encountered during the generation of the results.  
http://www.hardhats.org/fileman/pm/db_dic_l.htm
http://www.hardhats.org/fileman/pm/db_dicf.htm

Eighth parameter (index) of LIST^DIC can now be either a sort template or a field or a computed expression, if the new X flag is included. http://www.hardhats.org/fileman/pm/db_dic_l.htm

U flag on ^DIC and Q flag on LIST^DIC and FIND^DIC and partial numeric matches on pointer values
Previously, using the U flag on ^DIC and the Q flag on DBS DIC calls caused numeric matches on pointer fields to be partially matched a la text matches. Now, partial numeric matches are not allowed in these circumstances.

## New API to Create Sort Templates Silently
BUILDNEW^DIBTED will silently create a sort template.
http://www.hardhats.org/fileman/pm/db_intro.htm

# Data Dictionary Changes
## Auditable Word Processing Fields
Fileman security has been improved by allowing word­processing fields to be audited.
http://www.hardhats.org/fileman/u2/au_field.htm#Setting

## Word Processing Fields Can be Made Uneditable
Reference files and clinically significant text can now be protected from subsequent change.
http://www.hardhats.org/fileman/u2/ut_unedt.htm

## Set Explicit Maximum Length for Free-text Fields
Maximum Field Length is now an independent field attribute, not just a
side­effect of the code contained in the field’s Input Transform.

## Override of Character Limit in Globals
^DD(“STRING_LIMIT”), if set, overrides the standard 255­character limit throughout File Manager.

## Set Cross-references as Non-re-runnable
Cross­references can be defined so that they are never refired after their
initial execution (Remedy ticket #447336).

# Installation and Distribution Changes
DIFROM: Keys and New-style Indexes
DIFROM has been extended to be able to transport keys and new­style indexes
http://www.hardhats.org/fileman/pm/di_intro.htm

# DINIT: Virgin Install
Fileman has been changed to restore its ability to run correctly without any of
the rest of VISTA being installed.
http://www.hardhats.org/fileman/u2/pm_dinit.htm

# Bug Fixes
## Computed Expressions: Multiple Contains with Word-processing Fields

The computed expression (WP1["GREEN")!(WP2["GREEN") is now correctly handled (where WP1 and WP2 are names of Word­processing fields).

## Lookup: Input Value Longer Than 30 Characters
Lookups with input values longer than 30 characters now work correctly.

## Cross-reference a Field or File: Duplicate Index Names
Duplicate index names are no longer allowed.

## Uppercasing
Fileman uppercasing code in DILIBF is now User Language aware. Previously it worked only for English only.

## DIFROM Maximum Routine Size
DIFROM didn't use ^DD(“ROU”) to determine the maximum routine size, but rather had it hard­coded to 9999.
http://www.hardhats.org/fileman/pm/pu_dif4j.htm

## DIFROM Routine size calculation
DIFROM didn't correctly count the size of routines it created making routines larger than the maximum size.

## Browser display routines didn't work on Cache
DR^DDBRU didn't work on Cache due to the way %RSEL works on Cache.

## Maximum routine size did not get set with the first installation of Fileman.
The node ^DD(“ROU”) does not get initialized when installing Fileman for the first time.

## Browser now works without Kernel
The Fileman Browser now works without the device file and can be invoked from Fileman directly.

## Replace/With Maximum Length
The replace prompt only supported input up to 245 characters long. Now it supports any length up to ^DD(“STRING_LIMIT”)

## Reverse collation on Complex New Style Indexes when doing partial matches
Previously, a compound new style index configured to sort in reverse order still sorted in forward order upon partial matches even when it sorted in reverse when listing entries using “??”. Now, it will correctly sort in reverse order when displaying partial matches.
