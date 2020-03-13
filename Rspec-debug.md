# Appendix: How to debug Ruby in VS Code

1. Make sure ruby and gem is installed 
2. Search `Ruby` in Extensions Marketplace (the 5th icon in left vertical bar)  in and install that 
3. `gem install ruby-debug-ide` in any terminal
4. Search for "settings" in Help menu, and in the settings look for "Edit in settings.json", click on that
5. Paste the following into front within the curly bracket of that json file:
```python
"launch": {
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Debug RSpec",
            "type": "Ruby",
            "request": "launch",
            // replace it with your path of rspec program
            "program": "/usr/local/bin/rspec", 
            "args": [
                "${file}"
            ],
        },
        {
            "name": "Debug Current File",
            "type": "Ruby",
            "request": "launch",
            "cwd": "${workspaceRoot}",
            "program": "${file}"
        },
    ]
},
```

**The above steps you only have to do it once, next time you can just select the config "Debug Current File" or "Debug RSpec"**
5. Open the ruby / Rspec file you want to debug on, and then click on the bug icon on left bar (the 4th one)
6. If you are debugging with ruby file instead of rSpec, ,ake sure your code has an example rather than just definition, such as `p foo()`, and then click on the green arrow next to "DEBUG AND RUN" or just press F5 anytime. 
7. You can also add a breakpoint somewhere in your ruby file (click on the left of the line you want to start debugging with, and there will be red dot). Then you can start doing things like "next" "step" "continue"




