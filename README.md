Guide for C# in Godot:
[Godot Docs for C#](https://docs.godotengine.org/en/stable/tutorials/scripting/c_sharp/c_sharp_basics.html)
[Video tutorial I followed](https://www.youtube.com/watch?v=Yi1iIM-B7XQ&ab_channel=Gamefromscratch)

Download .NET version of Godot:
[Godot .NET download](https://godotengine.org/download/windows/)

Install latest version of .NET
[.NET download 8.0.302]https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-8.0.302-windows-x64-installer()

1. In vscode, install c# dev tools extensions

2. In vscode, f1 -> Sign into .NET for vscode with microsoft account

3. In vscode, ctrl+shift+p -> reload -> Reload window to restart VSCode window

4. In Godot, Create a new godot project

5. In Godot, Create a scene and add a new script

 - When creating a new script, choose C# instead of GDScript

6. In Godot, Build and run the scene, choose main file

7. In Godot, Project -> Tools -> C# -> Create C# Solution


.vscode/launch.json:
```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Run Godot CSharpTest",
            "type": "coreclr",
            "request": "launch",
            "preLaunchTask": "build",
            "program": "C:/Program Files (x86)/Godot/Godot_v4.2.2-stable_mono_win64/Godot_v4.2.2-stable_mono_win64.exe",
            "cwd": "${workspaceFolder}",
            "console": "internalConsole",
            "stopAtEntry": false,
            "args": ["--path", "${workspaceRoot}"]
        }
    ]
} 

```

.vscode/tasks.json:
```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "build",
            "command": "dotnet",
            "type": "shell",
            "args": [
                "build",
                // Ask dotnet build to generate full paths for file names.
                "/property:GenerateFullPaths=true",
                // Do not generate summary otherwise it leads to duplicate errors in Problems panel
                "/consoleloggerparameters:NoSummary"
            ],
            "group": "build",
            "presentation": {
                "reveal": "silent"
            },
            "problemMatcher": "$msCompile"
        }
    ]
}
```