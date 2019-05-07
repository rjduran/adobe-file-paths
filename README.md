# file-paths

A quick reference to common file paths for various 2D/3D design software packages

## Table of Contents

* [Adobe Illustrator](#adobe-illustrator) 
* [Autodesk Fusion 360](#autodesk-fusion-360) 
<!-- * [McNeel Rhino](#mcneel-rhino) 
* [Grasshopper](#grasshopper)  -->


## Adobe Illustrator

**Illustrator File Paths**

* Illustrator CC 2017 = version 21
* Illustrator CC 2018 = version 22
* Illustrator CC 2019 = version 23

### WINDOWS

**Adobe CEP**

```
User: C:\Users\<username>\AppData\Roaming\Adobe\<CEPVersion>\extensions\
System: C:\Program Files (x86)\Common Files\Adobe\<CEPVersion>\extensions\
```

**Swatches**

```
C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 22 Settings\en_US\x64\Swatches
```

**Symbols**

```
C:\Users\<username>\AppData\Roaming\Adobe\Adobe Illustrator 22 Settings\en_US\x64\Symbols
```

### MACOS

**Adobe CEP**

```
User: ∼/Library/Application Support/Adobe/<CEPVersion>/extensions
System: /Library/Application Support/Adobe/<CEPVersion>/extensions
```

**Swatches**

```
/Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 22/en_US/Swatches
```

**Symbols**

```
/Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 22/en_US/Symbols
```

**TIP:** It’s useful to manage shared swatches and symbols using symbolic links from a shared folder such as Dropbox to the Symbols or Swatches Adobe folder. 

For Example:

```
Source: /Users/<username>/Dropbox/Illustrator/SharedSymbols
Destination: /Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 22/en_US/Symbols
```

This makes a symbolic link from source to destination:

```
ln -s /Users/<username>/Dropbox/Illustrator/SharedSymbols /Users/<username>/Library/Application\ Support/Adobe/Adobe\ Illustrator\ 22/en_US/Symbols
```

## Autodesk Fusion 360

### WINDOWS

**Add-Ins**

```
C:\Users\<username>\AppData\Roaming\Autodesk\Autodesk Fusion 360\API\AddIns
```

**Scripts**

```
C:\Users\<username>\AppData\Roaming\Autodesk\Autodesk Fusion 360\API\Scripts
```

### MAC

**Add-Ins**

```
~/Library/Application Support/Autodesk/Autodesk Fusion 360/API/AddIns
```

**Scripts**

```
~/Library/Application Support/Autodesk/Autodesk Fusion 360/API/Scripts
```







