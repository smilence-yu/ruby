# How to debug Ruby in VS Code

 1. Search `Ruby` in Extensions Marketplace in and install that (the 5th icon in left vertical bar)
 2. `gem install ruby-debug-ide` in any terminal
 3. Click on the bug icon (4th icon) in left bar, and click on the link to "create a launch.json file"
 4. Paste the following into the json file:
```java
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "RSpec - active spec file only",
            "type": "Ruby",
            "request": "launch",
            "program": "/usr/local/bin/rspec",
            "args": ["${file}"],
        },
        {
            "name": "Debug Local File",
            "type": "Ruby",
            "request": "launch",
            "cwd":"${workspaceRoot}",
            "program": "${file}"
        },
    ]
}
```

**The above steps you only have to do it once, next time you can just select the config "Debug Local File" or  from dropdown menu when you open the `launch.json`**

 5. Add a breakpoint somewhere in your ruby file (click on the left of the line you want to start debugging with, and there will be red dot), Open the ruby / Rspec file you want to debug on, and then click on the bug icon on left bar
 6. Make sure your code has an example rather than just definition, such as `p foo()`, and then click on the green arrow next to "DEBUG AND RUN" or press F5. Then you can start doing things like "next" "step" "continue"
