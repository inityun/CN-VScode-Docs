# Using .NET in Visual Studio Code

.NET provides a fast and modular platform for creating many different types of applications that run on Windows, Linux, and macOS. Use Visual Studio Code with the C# and F# extensions to get a powerful editing experience with C# IntelliSense, F# IntelliSense (smart code completion), and debugging.

## Setting up VS Code for .NET development

### .NET Coding Pack

To help you set up quickly, you can install the .NET Coding Pack, which includes VS Code, the .NET Software Development Kit, and essential .NET extensions. The Coding Pack can be used as a clean installation, or to update or repair an existing development environment.

[Install the .NET Coding Pack - Windows](https://aka.ms/dotnet-coding-pack-win)

[Install the .NET Coding Pack - macOS](https://aka.ms/dotnet-coding-pack-mac)

    Note: The .NET Coding Pack is only available for Windows and macOS. For other operating systems, you will need to manually install the .NET SDK, VS Code, and .NET extensions.

### Installing extensions

If you are an existing VS Code user, you can also add .NET support by installing the .NET Extension Pack, which includes these extensions:

- C# for Visual Studio Code
- Ionide for F#
- Jupyter Notebooks
- Polyglot Notebooks

[Install the .NET Extension Pack](vscode:extension/ms-dotnettools.vscode-dotnet-pack)

You can also install extensions separately.

## Installing the .NET Software Development Kit

If you download the extensions separately, ensure that you also have the .NET SDK on your local environment. The .NET SDK is a software development environment used for developing .NET applications.

[Install the .NET SDK](https://aka.ms/vscDocs/dotnet/download)

## Create a C# "Hello World" app

1. Initialize a C# project:
    - Open a terminal/command prompt and navigate to the folder in which you'd like to create the app.
    - Enter the following command in the command shell:  
    ```
    dotnet new console
    ```

2. When the project folder is first opened in VS Code:
    - A "Required assets to build and debug are missing. Add them?" notification appears at the bottom right of the window.
    - Select Yes.

3. Run the app by entering the following command in the command shell:
    ```
    dotnet run
    ```

## Create an F# "Hello World" app

1. Initialize an F# project:
    - Open a terminal/command prompt and navigate to the folder in which you'd like to create the app.
    - Enter the following command in the command shell:
    ```
    dotnet new console -lang "F#"
    ```

2. Once it completes, open the project in Visual Studio Code:
    ```
    code .
    ```

3. Run the app by entering the following command in the command shell:
    ```
    dotnet run
    ```

## Next steps

- Continue exploring C# development: Debug with VS Code and .NET
- Basic Editing - Learn about the powerful VS Code editor.
- Code Navigation - Move quickly through your source code.
- Working with C# - Learn about the great C# support you'll have when working on your .NET application.
- Tasks - Running tasks with Gulp, Grunt, and Jake. Showing Errors and Warnings
- .NET Docs - Visit the .NET docs for more information on this powerful cross-platform development solution.
- Deploying Applications to Azure - Deploy your app to Azure.
- Get Started with F# in Visual Studio Code