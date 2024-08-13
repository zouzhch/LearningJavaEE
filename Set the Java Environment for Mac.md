- the version number of Java 8 is Java 1.8,
- the files will be installed in three places. If you want to omit them, type in these commands:
```shell
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk1.8.0_71.jdk
sudo rm -rf /Library/PreferencePanes/JavaControlPanel.prefPane
sudo rm -rf /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin
```

- so-called the environment variable is just for the **SHELL,**
- the SHELL will load the configuration file named ".bash_profile" whenever it's been called,
   - pay attention to the initial dot of the file name, it means the file is hidden
## set the Java environment for the SHELL command line:
in the .bash_profile, we set a JAVA_HOME variable like this:
```shell
JAVA_HOME=/Users/zouzhch/Library/Java/JavaVirtualMachines/corretto-1.8.0_422/Contents/Home
```

- the "zouzhch" in the path is the user name of the Mac

then we can invoke the variable by adding a $ in the front of a variable: $JAVA_HOME,
and set the PATH variable like this:
```shell
PATH=$JAVA_HOME/bin:$PATH:.
```
in the PATH variable, we use ":" to separate different paths.
So we invoke self by $PATH to add other paths that have been added before.

the SHELL command as below will load the profile immediately:
```shell
source .bash_profile
```
but it will lose efficacy when we shut the SHELL window.
so we can create a .zshrc file, and add the command below to it: 
```shell
source .bash_profile
```
then it will load the profile automatically whenever the SHELL starts.

