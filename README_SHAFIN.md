# Using original repo with apache netbeans

All issues, except "beans-binding not found" can be straightforwardly resolved by netbeans (as of version 11.0).
If there is error like "failed to download nbjavac", install plugin from [this file](z10215_org-netbeans-modules-nbjavac-impl.nbm).

To resolve "beans-binding not found", right click on project file -> properties -> 3 dots beside classpath -> Add jar/folder -> select [this file](beansbinding-1.2.1.jar).

## Getting jar

From clean and build in netbeans, jar will be made in dist/Hightail-combined.jar.

## Using jar from launcher

### Ubuntu

- Make [this jar](Hightail/dist/Hightail-combined.jar) executable
- From terminal: ```sudo apt install alacarte```
- launch alacarte / "main menu" app, Applications->Programming->New Item->Name: Hightail, Command: java -jar /full/path/to/[this jar](Hightail/dist/Hightail-combined.jar), click on the icon at left side: choose [this file](Hightail/src/org/hightail/ui/resources/button-green.png)

### Windows

- Create a shortcut for your .JAR, then right click and go to properties Edit the target to match this format:
%SystemRoot%\explorer.exe "path to jar", or %SystemRoot%\system32\cmd.exe /C "path to jar", or javaw -jar C:\Path\To\My\Program.jar (Additionally, specify the Start in path to C:\Path\To\My if your Java program uses relative paths to reference external files.).
- Finally, pin your new shortcut to the taskbar by dragging it there. The icon will be the same as CMD but you can easily change it:
right click -> properties -> Shortcut tab -> Change Icon... -> choose [this file](button-green.ico).

# Using original repo with intellij

Firstly, try to always compile using netbeans, actually try to completely avoid intellij.
Intellij open using the folder which contains src immediately as child.
Go to project structure->modules, mark src as source root, test as test root, dependencies->mark lib folder.
Don't use ant in Intellij (it causes unfixable bugs sometimes), use from terminal: ant:
If it shows failed in test case x, delete that test case, our desired jar is dist/hightail-combined.jar.