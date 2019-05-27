# adobe-file-paths

A quick reference to common file paths and ways of sharing assets for Adobe Creative Cloud.

## Table of Contents

* [Adobe Illustrator](#adobe-illustrator)
    * [Windows Paths](#windows-paths)
        * Swatches
        * Symbols
        * Brushes
        * Scripts
        * Adobe CEP
    * [Sharing Assets on Windows](#sharing-assets-on-windows)
    * [MacOS Paths](#macos-paths)
        * Swatches
        * Symbols
        * Brushes
        * Scripts
        * Adobe CEP
    * [Sharing Assets on MacOS](#sharing-assets-on-macos)
* [References](#references)
<!-- * Adobe Photoshop -->
<!-- * Adobe After Effects -->


## Adobe Illustrator

**Versions**

* Illustrator CC 2017 = version 21
* Illustrator CC 2018 = version 22
* Illustrator CC 2019 = version 23

_Be sure to replace the Illustrator version number below with the version being used._

### Windows Paths

**Swatches**

Preset swatches:
```
C:\Program Files\Adobe\Adobe Illustrator CC 2019\Presets\en_US\Swatches
```

Custom swatches:
```
C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 23 Settings\en_US\x64\Swatches
```

**Symbols**

Preset symbols:
```
C:\Program Files\Adobe\Adobe Illustrator CC 2019\Presets\en_US\Symbols
```

Custom symbols:
```
C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 23 Settings\en_US\x64\Symbols
```

**Brushes**

Preset brushes:
```
C:\Program Files\Adobe\Adobe Illustrator CC 2019\Presets\en_US\Brushes
```

Custom brushes:
```
C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 23 Settings\en_US\x64\Brushes
```

**Adobe CEP**

These folders are where Illustrator looks for custom CEP plugins. Check out [adobe-cep](https://github.com/rjduran/adobe-cep) to learn more.

```
User: C:\Users\<username>\AppData\Roaming\Adobe\<CEPVersion>\extensions\
System: C:\Program Files (x86)\Common Files\Adobe\<CEPVersion>\extensions\
```

### Sharing Assets on Windows

To share assets (Swatches, Brushes, Symbols) across directories on Windows there are two options:

1. Use the built in presets directory found at `C:\Program Files\Adobe\Adobe Illustrator CC 2019\Presets\en_US\<asset-type>`. _Note: In the preset assets folders you will probably find all the existing presets. I put these files into a folder named "Adobe" that lives along side any custom asset folders I add to keep it organized._
2. Use the custom "user defined" directory found at `C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 23 Settings\en_US\x64\<asset-type>`.

    _Note: I should mention it is possible to share all assets in the cloud using the Adobe infrastructure but you don't have local access to collections of assets if developing extensions or just making libraries to share internally. These instructions are for anyone interested in working locally or with shared assets._

**Method 1: Shortcuts**

Shortcuts can be used to make a link between two directories, such as a Dropbox directory and the Presets system directory. This kind of link could be used in place of symbolic links on Windows systems and are useful for admin level directories. Also, the benefit of using them in this way means that brushes, swatches, or symbols will show up in the list of each kind based on the directory name and asset collection name. 

**For Example: Making a shortcut between directory A and directory B**

Directory A: `C:\Users\<username>\Dropbox\Templates\Symbols\SharedSymbols`<br>
Directory B: `C:\Program Files\Adobe\Adobe Illustrator CC 2019\Presets\en_US\Symbols`

Make a shortcut by right clicking on the SharedSymbols directory and select "Create shortcut". A shortcut named "SharedSymbols - shortcut" will be created. Remove the shortcut part of the filename and move to Directory B. You will need to have Admin access to move the shortcut. Once this is done, open Illustrator and goto the Symbols panel to see the SharedSymbols item in the list.

**Method 2: Symbolic Links**

Symbolic links can be used to make a link between a custom directory, say in a Dropbox, with the custom "user defined" system folder. This kind of link will put brushes, swatches, or symbols into the User Defined menu item at the bottom of each type of asset panel. 

**For Example: Making a symbolic link between directory A and directory B**

Directory A: `C:\Users\<username>\Dropbox\Templates\Symbols\SharedSymbols`<br>
Directory B: `C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 23 Settings\en_US\x64\Symbols`

```
ln -s /c/Users/<username>/Dropbox/Templates/Symbols/SharedSymbols /c/Users/<username>/AppData/Roaming/
Adobe/Adobe\ Illustrator\ 23\ Settings/en_US/x64/Symbols
```

Tip: To create symlinks as shown above I am using [cmder](https://cmder.net/) terminal emulator.

### MacOS Paths

**Swatches**

Preset swatches:
```
/Applications/Adobe\ Illustrator\ CC\ 2019/Presets.localized/en_US/Swatches
```

Custom swatches:
```
/Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 23/en_US/Swatches
```

**Symbols**

Preset symbols:
```
/Applications/Adobe\ Illustrator\ CC\ 2019/Presets.localized/en_US/Symbols
```

Custom symbols:
```
/Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 23/en_US/Symbols
```

**Brushes**

Preset brushes:
```
/Applications/Adobe\ Illustrator\ CC\ 2019/Presets.localized/en_US/Brushes
```

Custom brushes:
```
/Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 23/en_US/Symbols
```

**Scripts**

The scripts folder recognized by Illustrator doesn't acknowledge symlinks or aliases. Therefore, the best way to manage scripts is to keep them in the default folder for the version of Illustrator being used. To keep this folder organized one could use sub folders for any group of scripts. These show up as nested items in the _File > Scripts_ menu item. [Per the Adobe Illustrator CC 2017 Scripting Guide (pg 10)](https://www.adobe.com/content/dam/acom/en/devnet/illustrator/pdf/AI_ScriptGd_2017.pdf), one could also just reference a script anywhere on the system via _File > Scripts > Other Script_. 

New to scripting? To learn more about scripting in general, check out [adobe-scripting](https://github.com/rjduran/adobe-scripting) to learn more.

Preset scripts:
```
/Applications/Adobe\ Illustrator\ CC\ 2019/Presets.localized/en_US/Scripts
```

**Adobe CEP**

These folders are where Illustrator looks for custom CEP plugins. Check out [adobe-cep](https://github.com/rjduran/adobe-cep) to learn more.

```
User: ∼/Library/Application Support/Adobe/<CEPVersion>/extensions
System: /Library/Application Support/Adobe/<CEPVersion>/extensions
```


### Sharing Assets on MacOS

It’s useful to manage shared assets using symbolic links from a shared folder such as Dropbox to the Symbols or Swatches Adobe folder. 

For Example:

```
Source: /Users/<username>/Dropbox/Illustrator/SharedSymbols
Destination: /Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 23/en_US/Symbols
```

This makes a symbolic link from source to destination:

```
ln -s /Users/<username>/Dropbox/Illustrator/SharedSymbols /Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 23/en_US/Symbols
```

