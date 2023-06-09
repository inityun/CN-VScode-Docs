---
Order: 4
Area: languages
TOCTitle: C++
ContentId: D06C8C5C-2D3A-4B2E-B31F-12F1907E6402
PageTitle: C++ programming with Visual Studio Code
DateApproved: 9/7/2016
MetaDescription: Find out how to get the best out of Visual Studio Code and C++.
---

# C/C++ for VS Code (预览)(Preview)

C/C++ support for Visual Studio Code is provided today as a preview of our work to enable cross-platform C and C++ development using VS Code on Windows, Linux, and OS X. Our focus in this preview release is code editing and navigation support for C and C++ code everywhere that VS Code runs, as well as debugging on Linux, OS X, and Windows.

今天作为我们工作的预览，C/C++ support for VS Code 被提供出来。它能够在Windows，Linux和OS X上跨平台开发C和C++。 我们这个预览版的重点是代码编辑和在任何运行VS Code中的C 和 C++ 的代码导航，以及在Linux，OS X和Windows下的调试

If you just want a lightweight tool to edit your C++ files, VS Code has you covered but if you want the best possible experience for your existing Visual C++ projects or debugging on Windows, we recommend you use a version of Visual Studio such as [Visual Studio Community](https://www.visualstudio.com/products/visual-studio-community-vs).

如果你只是想一个轻量级的工具来编辑你的C++文件，无论你在哪里VSCode都已经被覆盖。但如果你想在Windows下调试您现有的Visual C ++项目，最佳的体验，我们推荐您使用[Visual Studio社区]版本的Visual Studio。

We're still shaping the C++ experience in VS Code so now is a great time to [provide bug reports, feature requests, and feedback](mailto:c_cpp_support@microsoft.com), and for those of you who use Linux or OS X as your development environment, to [get engaged](http://landinghub.visualstudio.com/c-nonwin) with the Visual Studio team.

我们仍然在塑造在VS code中编写C++的体验，所以现在是个[提交bug报告，特性要求，以及反馈](mailto:c_cpp_support@microsoft.com)的好机会。对于那些使用Linux或者OS X作为你的开发环境的开发者，请到[get engaged](http://landinghub.visualstudio.com/c-nonwin)为Visual Studio团队提供反馈。

## Getting Started（开始）

**To install the Microsoft C/C++ extension:**

**安装微软的C/C++拓展**

* Open VS Code.
* 打开VS code。


* Click the Extensions View icon on the Sidebar.
* 点击在侧边栏的查看拓展的图标


* Search for `cpptools`.
* 查找`cpptools`


* Click **Install**, then click **Enable**.
* 点击**Install（安装）**，然后点击**Enable（可用）**


* Open a folder that contains your C/C++ code.
* 打开一个包含你的C/C++文件的文件夹


**To enable code completion and navigation, you will need to generate a `c_cpp_properties.json` file:**

**为了启用代码补齐和导航，你需要生成一个`c_cpp_properties.json`文件：**

* Hover over any green squiggle in a source file (e.g. a #include statement).
* 在源文件中，讲鼠标悬停在绿色的波浪上（比如一个#include语句）


* Click the lightbulb that appears underneath the mouse cursor.
* 点击在鼠标之下出现的灯泡的图案


* Click **Add include path to settings**.
* 点击**Add include path to settings**

This will generate a `c_cpp_properties.json` file that allows you to add additional include paths to properly enable code navigation and auto-completion.

这样会生成一个允许你添加include paths以正确启用代码导航和自动补齐功能的`c_cpp_properties.json`文件

>**Note:** You can also generate or edit a `c_cpp_properties.json` file with the **C/Cpp: Edit Configurations** command from the __Command Palette__ (`Ctrl+Shift+P or F1`).

>**备注：**你也可以从 __命令面板__ (`Ctrl+Shift+P or F1`)中通过**C/Cpp: Edit Configurations**命令来生成或编辑`c_cpp_properties.json`文件

**If you want to build your application from VS Code, you will need to generate a `tasks.json` file:**

**如果你想从VS code中构建你的应用，你需要生成一个`tasks.json` 文件：**

* Open the **Command Palette** (`Ctrl+Shift+P or F1`).
* 打开**命令面板**(`Ctrl+Shift+P or F1`).


* Select the **Tasks: Configure Task Runner** command and you will see a list of task runner templates.
* 选择**Tasks: Configure Task Runner** command，你将会看到一个进程执行器模板（task runner templates）列表


* Select **Others** to create a task which runs an external command.
* 选择**Others**创建一个执行外部命令的进程


* Change the `command` to the command line expression you use to build your application (e.g. `g++ -g main.cpp`).
* 修改`command`选项为在命令行环境下你创建编译应用的表达式（比如`g++ -g main.cpp`）


* Add any required args (e.g. `-g` to build for debugging).
* 添加任何必要的参数


* You can now build your application with (`ctrl+shift+b`)
* 现在你可以通过(`ctrl+shift+b`)构建你的应用了

You should now see a `tasks.json` file in your workspace `.vscode` folder that looks something like:

现在你应该可以在你的工作目录的`.vscode`文件夹下找到一个内容像下面展示那样的`tasks.json`文件：

```json
{
    "version": "0.1.0",
    "command": "g++",
    "isShellCommand": true,
    "showOutput": "always",
    "args": ["-g", "main.cpp"]
}
```

For more information on tasks, see [Integrate with External Tools via Tasks](/md/编辑器/任务.md).

**To enable debugging, you will need to generate a `launch.json` file:**

**为了能够调试，你需要生成一个`launch.json`文件：**

* Navigate to the Debug view by clicking the Debug icon in the Sidebar.
* 通过点击在侧边栏的调试图标，可以导航到调试窗口


* In the **Debug** view, click the **Configure** icon.
* 在**调试窗口**，点击**设置**图标


* Select `C++ (GDB/LLDB)` (to use GDB or LLDB) or `C++ (Windows)` (to use the Visual Studio Windows Debugger) from the **Select Environment** dropdown. This creates a `launch.json` file for editing with two configurations:
* 从选择环境的选项中选择`C++ (GDB/LLDB)`（使用GDB或LLDB）或`C++ (Windows)`（使用Visual Studio Windows Debugger），这会创建一个`launch.json` 文件，用来编辑两个设置
  * **C++ Launch** defines the properties for launching your application when you start debugging.
  * **C++ Launch** 定义了当你开始调试时用来启动应用的属性
  * **C++ Attach** defines the properties for attaching to 
  a process that's already running.
  * **C++ Attach**  定义了将应用附加到早已运行的线程时的属性


* Update the `program` property with the path to the program you are debugging.
* 把`program` 属性更新为你要调试的程序的路径


* If you want your application to build when you start debugging, add a `preLaunchTask` property with the name of the build task you created in `tasks.json` ("g++" in the example above).
* 如果你想开始调试时构建应用的话，添加一个`preLaunchTask` 属性，其值为你在`tasks.json`文件里创建的生成任务的名称。

To learn more, see [Configuring launch.json for C/C++ debugging](https://github.com/Microsoft/vscode-cpptools/blob/master/launch.md).

If you are debugging with GDB on Windows, see [Windows Debugging on Cygwin/MinGW](#debug_windows_gdb).

## Editing Code

### Code Formatting

The C/C++ extension for Visual Studio Code supports source code formatting using [clang-format](http://clang.llvm.org/docs/ClangFormat.html) which is included with the extension.

You can format an entire file or just the current selection with the **Format Code** command (`Shift+Alt+F`) in right-click context menu. You can also configure auto-formatting with the following [settings](/md/定制化/用户和工作空间.md):

* `C_Cpp.clang_format_formatOnSave` - to format when you save your file.
* `editor.formatOnType` - to format as you type (triggered on the `;` character).

By default, the clang-format style is set to "file" which means it looks for a `.clang-format` file inside your workspace. If the `.clang-format` file is found, formatting is applied according the settings specified in the file. If no `.clang-format` file is found in your workspace, formatting is applied according to a default style specified in the `C_Cpp.clang_format_fallbackStyle` [setting](/md/定制化/用户和工作空间.md) instead. Currently, the default formatting style is "Visual Studio". Using "Visual Studio" formatting ensures that source code formatting will be compatible in both VS Code and Visual Studio Community.

The "Visual Studio" clang-format style is not yet an official OOTB clang-format style but it implies the following clang-format settings:

```json
UseTab: (VS Code current setting)
IndentWidth: (VS Code current setting)
BreakBeforeBraces: AllMan
AllowShortIfStatementsOnASingleLine: false
IndentCaseLabels: false
ColumnLimit: 0
```

If you'd like to use a different version of clang-format than the one that ships with the extension, you can use the `C_Cpp.clang_format_path` [setting](/md/定制化/用户和工作空间.md) and set its value to the path where the clang-format binary is installed.

For example on the Windows platform:

```json
  "C_Cpp.clang_format_path": "C:\\Program Files (x86)\\LLVM\\bin\\clang-format.exe"
```

### Fuzzy Auto-Complete (preview)

Fuzzy auto-complete is powered by an enhanced tag-parser approach. Although suggestions are not based on semantic analysis of your code, this feature provides a wider selection of matches than the single-file IntelliSense experience provided today.

In particular, this feature's capabilities give a good experience for C code.

## Navigating Code

The source code navigation features provided by the C/C++ extension are powerful tools for understanding and getting around in your codebase. These features are powered by tags stored in an offline database of symbol information (in the file `browse.VC.db`). With the C/C++ extension installed, this database is generated whenever a folder containing C++ source code files is loaded into VS Code. The platform indicator (Win32 in the figure below) turns red and appears next to a flame icon while the tag-parser is generating this information.

![The platform indicator during tag parsing](images/cpp/parsing.png)

When the platform indicator returns to its normal appearance, the source code symbols have been tagged in the offline database and source code navigation features are ready to be used.

### Specifying Additional Include Directories for Better Symbol Support

To provide the best experience, the C/C++ extension for VS Code needs to know where it can find each header file referenced in your code. By default, the extension searches the current source directory, its sub-directories, and some platform-specific locations. If a referenced header file can't be found, VS Code displays a green squiggle underneath each #include directive that references it.

To specify additional include directories to be searched, place your cursor over any #include directive that displays a green squiggle, then click the lightbulb action when it appears. This opens the file `c_cpp_properties.json` for editing; here you can specify additional include directories for each platform configuration individually by adding more directories to its 'includePath' property.

![Adding an additional include path](images/cpp/includepath.gif)

### Search for Symbols

You can search for symbols in the current file or workspace to navigate your code more quickly.

To search for a symbol in the current file, press `Ctrl+Shift+O`, then enter the name of the symbol you're looking for. A list of potential matches will appear and be filtered as you type. Choose from the list of matches to navigate to its location.

![Searching the current file](images/cpp/filesearch.png)

To search for a symbol in the current workspace, start by pressing `Ctrl+T` instead, then enter the name of the symbol. A list of potential matches will appear as before. If you choose a match that was found in a file that's not already open, the file will be opened before navigating to the match's location.

![Searching in your workspace](images/cpp/workspacesearch.png)

Alternatively, you can search for symbols by accessing these commands through the __Command Palette__ if you prefer. Use __Quick Open__ (`ctrl+e`) then enter the '@' command to search the current file, or the '#' command to search the current workspace. `Ctrl+Shift+O` and `ctrl+t` are just shortcuts for the '@' and '#' commands, respectively, so everything works the same.

### Peek Definition

You can take a quick look at how a symbol was defined by using the Peek Definition feature. This feature displays a few lines of code near the definition inside a peek window so you can take a look without navigating away from your current location.

To peek at a symbol's definition, place your cursor on the symbol anywhere it's used in your source code and then press `Alt+F12`. Alternatively, you can choose __Peek Definition__ from the context menu (right-click, then choose __Peek Definition__).

![Peek definition](images/cpp/peekdefn.png)

Currently, the C/C++ extension doesn't parse code in a way that helps it distinguish between competing definitions based on how the symbol is used. These competing definitions arise when the symbol defines different things in different contexts, such as occurs with overloaded functions, classes and their constructors, and other situations. When this happens, each of the competing definitions are listed in the right-hand side of the peek window with the source code of the current selection displayed on the left.

With the peek window open, you browse the list of competing definitions to find the one you're interested in. If you want to navigate to the location of one of the definitions just double-click the definition you're interested in, or by double-clicking anywhere in the source code displayed on the left-hand side of the peek window. 

### Go to Definition

You can also quickly navigate to where a symbol is defined by using the Go to Definition feature.

To go to a symbol's definition, place your cursor on the symbol anywhere its used in your code and then press `F12`. Alternatively, you can choose __Go to Definition__ from the context menu (right-click, then choose __Go to Definition__). When there's only one definition of the symbol, you'll navigate directly to its location, otherwise the competing definitions are displayed in a peek window as described in the previous section and you have to choose the definition that you want to go to.

## Debugging

After you have set up the basics of your debugging environment as specified in [Getting Started](/md/语言/cpp.md#getting-started), you can learn more details about debugging C/C++ in this section.

VS Code supports the following debuggers for C/C++ depending on the operating system you are using:

* **Linux**: GDB
* **OS X**: LLDB or GDB
* **Windows**: the Visual Studio Windows Debugger or GDB (using Cygwin or MinGW)

### Windows Debugging with GDB on Cygwin/MinGW <a name="debug_windows_gdb"></a>

You can debug Windows applications created using Cygwin or MinGW by using VS Code. To use Cygwin or MinGW debugging features, the debugger path must be set manually in the launch configuration (`launch.json`). To debug your Cygwin or MinGW application, add the `miDebuggerPath` property and set its value to the location of the corresponding gdb.exe for your Cygwin or MinGW environment.

For example:

```json
    "miDebuggerPath": "c:\\mingw\\bin\\gdb.exe"
```

Cygwin/MinGW debugging on Windows supports both attach and launch debugging scenarios.

### Conditional Breakpoints

Conditional breakpoints enable you to break execution on a particular line of code only when the value of the condition is true. To set a conditional breakpoint, right-click on an existing breakpoint and select __Edit Breakpoint__. This opens a small peek window where you can enter the condition that must evaluate to true in order for the breakpoint to be hit during debugging.

![A conditional break](images/cpp/condbreak.png)

In the editor, conditional breakpoints are indicated by a breakpoint symbol that has a black equals sign inside of it. You can place the cursor over a conditional breakpoint to show its condition.

### Function Breakpoints

Function breakpoints enable you to break execution at the beginning of a function instead of on a particular line of code. To set a function breakpoint, on the __Debug__ pane right-click inside the __Breakpoints__ section, then choose __Add Function Breakpoint__ and enter the name of the function on which you want to break execution.

### Expression Evaluation

VS Code supports expression evaluation in several contexts:

* You can type an expression into the __Watch__ section of the __Debug__ panel and it will be evaluated each time a breakpoint is hit.
* You can type an expression into the __Debug Console__ and it will be evaluated only once.
* You can evaluate any expression that appears in your code while you're stopped at a breakpoint.

Note that expressions in the __Watch__ section take effect in the application being debugged; an expression that modifies the value of a variable will modify that variable for the duration of the program.

### Multi-threaded Debugging

The C/C++ extension for VS Code has the ability to debug multi-threaded programs. All threads and their call stacks appear in the __Call Stack__ section:

![Multi-threaded process](images/cpp/threads.png)

### Memory Dump Debugging

The C/C++ extension for VS Code also has the ability to debug memory dumps. To debug a memory dump, open your `launch.json` file and add the `coreDumpPath` (for GDB or LLDB) or `dumpPath` (for the Visual Studio Windows Debugger) property to the __C++ Launch__ configuration, set its value to be a string containing the path to the memory dump. This will even work for x86 programs being debugged on an x64 machine.

### Additional Symbols

If there are additional directories where the debugger can find symbol files (e.g., `.pdb` files for the Visual Studio Windows Debugger), they can be specified by adding the `additionalSOLibSearchPath` (for GDB or LLDB) or `symbolSearchPath` (for the Visual Studio Windows Debugger).

For example:

```json
    "additionalSOLibSearchPath": "/path/to/symbols;/another/path/to/symbols"
```
or

```json
    "symbolSearchPath": "C:\\path\\to\\symbols;C:\\another\\path\\to\\symbols"
```


### GDB, LLDB and MI Commands (GDB/LLDB)

For the `C++ (GDB/LLDB)` debugging environment, you can execute GDB, LLDB and MI commands directly through the debug console with the `-exec` command, but be careful, executing commands directly in the debug console is untested and might crash VS Code in some cases.

### Other Debugging Features

* Unconditional breakpoints
* Watch window
* Call stack
* Stepping

 For more information on debugging with VS Code, see this introduction to [debugging in VS Code](/md/编辑器/调试.md).

## Known Limitations

### Symbols and Code Navigation

All platforms:

* Because the extension doesn't parse function bodies, Peek Definition and Go to Definition don't work for symbols defined inside the body of a function.

### Debugging

All platforms:
* There is no way to specify the source file mappings from the compiled locations to the current location. This prevents debugging an application in a different file system layout than where it was compiled.

Windows:

* GDB on Cygwin and MinGW cannot break a running process. To set a breakpoint when the application is running (not stopped under the debugger), or to pause the application being debugged, press `Ctrl-C` in the application's terminal.
* GDB on Cygwin cannot open core dumps.

Linux:

* GDB needs elevated permissions to attach to a process. When using *attach to process*, you need to provide your password before the debugging session can begin.

OS X:

* LLDB:
    * When debugging with LLDB, if the Terminal window is closed while in break mode, debugging does not stop. Debugging can be stopped by pressing the **Stop** button.
    * When debugging is stopped the Terminal window is not closed.
* GDB:
    * Additional manual install steps need to be completed to use GDB on OS X. See _Manual Installation of GDB for OS X_ in the [README](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools).
    * When attaching to a process with GDB, the application being debugged cannot be interrupted. GDB will only bind breakpoints set while the application is not running (either before attaching to the application, or while the application is in a stopped state). This is due to [a bug in GDB](https://sourceware.org/bugzilla/show_bug.cgi?id=20035).
    * Core dumps cannot be loaded when debugging with GDB because GDB [does not support the core dump format used in OS X](https://www.sourceware.org/ml/gdb/2014-01/msg00036.html).
    * When attached to a process with GDB, break-all will end the process.

## Next Steps

Read on to find out about:

* [Editing Evolved](/md/编辑器/与时俱进的编辑体验.md) - find out more about advanced editing features
* [Tasks](/md/编辑器/任务.md) - use tasks to build your project and more
* [Debugging](/md/编辑器/调试.md) - find out how to use the debugger with your project

## Common Questions

**Q: My project won't load.**

**A:** VS Code doesn't currently support C++ project files, instead it considers a directory of your choosing to be the workspace of your project. Source code files inside that directory and its sub-directories are part of the workspace.

**Q: IntelliSense isn't working.**

**A:** In this release, IntelliSense isn't supported. We plan to enable this and other features in future releases.

**Q: How do I build/run my project?**

**A:** VS Code supports tasks that you can configure to build your application, and natively understands the output of MSBuild, CSC, and XBuild. For more information, see the [Tasks](/md/编辑器/任务.md) documentation.

**Q: Why is there a .browse.VC.db file in my workspace?**

**A:** The C/C++ extension automatically creates a database of symbol information for your workspace and stores it in a `.browse.VC.db` file in your workspace's `.vscode` folder. This improves the extension's performance and this file should not be added to source control.

If you have any other questions or run into any issues, please file an issue on [GitHub](https://github.com/Microsoft/vscode-cpptools/issues).
