# FileUtils
![projectstage](https://img.shields.io/badge/project%20stage-release-green)
![projectstage](https://img.shields.io/badge/version-1.1-green)
[![license](https://img.shields.io/github/license/computercraft-package-tool/fileutils)](https://github.com/computercraft-package-tool/fileutils/blob/main/LICENSE)
[![issues](https://img.shields.io/github/issues/computercraft-package-tool/fileutils)](https://github.com/computercraft-package-tool/fileutils/issues)<br>
[![contributors](https://img.shields.io/github/contributors/computercraft-package-tool/fileutils)](https://github.com/computercraft-package-tool/fileutils/graphs/contributors)
[![activity](https://img.shields.io/github/commit-activity/m/computercraft-package-tool/fileutils)](https://github.com/computercraft-package-tool/fileutils/commits/main)
[![lastcommit](https://img.shields.io/github/last-commit/computercraft-package-tool/fileutils)](https://github.com/computercraft-package-tool/fileutils/commits/main)<br>
![size](https://img.shields.io/github/languages/code-size/computercraft-package-tool/fileutils)
![files](https://img.shields.io/github/directory-file-count/computercraft-package-tool/fileutils)
![languages](https://img.shields.io/github/languages/count/computercraft-package-tool/fileutils)<br>

Library for the Minecraft mod **ComputerCraft/CC: Tweaked** for better interaction with files  

## How to install 
FileUtils can be installed using the [ComputerCraft Package Tool](https://github.com/computercraft-package-tool/ccpt) by using the following commands:

Install CCPT, only run if you havn't installed it yet:
```
pastebin run syAUmLaF
```
Install the library:
```
ccpt install fileutils
```
The library will now be stored in "/lib/fileutils.lua".

## How to use

### 1. **Include in your project**

The FileUtils library can be included in your project by using the older ```dofile(...)```-method, or the newer ```require(...)```-method (availible only in [CC: Tweaked](https://tweaked.cc/)):

```lua
-- Using dofile(...)
local fileutils = dofile("/lib/fileutils.lua")
-- Using require(...)
local fileutils = require("lib.fileutils")
```

In both instances, the methods of the library can be accessed as members of the return value of the method, e.g. ```fileutils.readFile(...)```.

**Using *os.loadAPI("lib/fileutils")* in order to include the library won't work anymore!** See also [deprecation notice](https://tweaked.cc/module/os.html#v:loadAPI) of the method.

### **2. Store some content in a file**  
The function **storeFile([filepath],[content])** stores [content], given as a string, in a file specified by the given [filepath]. This will overwrite the file if it already exists!

*Example:*  
Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/storeFile.png"
/><br> 
Content of *"test"*:
```
hi, how are you?
```

### **3. Read some content from a file**  
The function **readFile([filepath],[createnew])** reads a file specified by the given [filepath]. If [createnew] is nil and the file doesn't exist, false is returned. If [createnew] is some string and the file doesn't exist, a new file with the content [createnew] is created and [createnew] is returned. This is useful if you don't know wether the file was already created, and if not some basic file structure should be built.

*Examples:*<br>1) Content of *"test"*:
```
hi, how are you?
```
Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readFileFalseExists.png"
/><br> 
2) *"test"* does not exist.

Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readFileFalseMissing.png"
/><br> 
3) *"test"* does not exist.

Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readFileTrueMissing.png"
/><br> 
Content of *"test"*:
```
:)
```

### **4. Store a table in a file**  
The function **storeData([filepath],[content])** stores [content], given as a table, in a file specified by the given [filepath]. This will overwrite the file if it already exists!

*Example:*  
Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/storeData.png"
/><br> 
Content of *"test"*:
```lua
{  greeting = "'ello",}
```
### **3. Read a table from a file**  
The function **readFile([filepath],[createnew])** reads a file specified by the given [filepath] as a table. If [createnew] is false and the file doesn't exist, false is returned. If [createnew] is true and the file doesn't exist, a new file with the content "{}" is created and an empty table is returned.

*Examples:*<br>1) Content of *"test"*:
```lua
{  greeting = "'ello",}
```
Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readDataFalseExists.png"
/><br> 
2) *"test"* does not exist.

Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readDataFalseMissing.png"
/><br> 
3) *"test"* does not exist.

Example code and output:
<br><img
    alt="missing image :("
    src="https://raw.githubusercontent.com/computercraft-package-tool/fileutils/main/img/readDataTrueMissing.png"
/><br> 
Content of *"test"*:
```
{}
```

## Changelog
**Version 1.1**
- ```file_exists(...)``` removed, just use ```fs.exists(path)``` instead (Also see the [CC: Tweaked documentation](https://tweaked.cc/module/fs.html#v:exists) of the method)
- Update method to include the library using ```dofile(...)``` or ```require(...)```, as ```os.loadAPI(...)``` is (rightfully) [deprecated]((https://tweaked.cc/module/os.html#v:loadAPI))
- Add ```.lua```-extension to the library file (syntax highlighting in editors etc.). The only reason we did not have this before is that file extensions did not work with ```os.loadAPI(...)```, which is no longer supported with FileUtils version 1.1 anyways.

## Last words
First of all, thanks for reading! This library is not the biggest library ever, but it turned out to be really useful for one of my projects, and maybe it is for yours too :)  
If you find bugs, please create an issue so I can fix them.  
I'm not that confident with GitHub yet, so feel free to point out things I could do better. Also, english is not my first language, so if you find any spelling/language-related mistakes, please do also create an issue.  
Have a nice day,  
PentagonLP
