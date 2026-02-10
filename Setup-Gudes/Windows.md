## Windows Setup
This is a guide to assit windows users with setting up the JS SDK on their local Windows machine.

### Use the steps below to setup the JS SDK
> [!Note]
> Please ensure you have a correct corepack configuration

1. Taskfile tool installation
   
   Exmaple commands: 
   ```
    # with npm
    $ npm install -g @go-task/cli
    
    # with homebrew
    $ brew install go-task
   ```
2. pNpm package manager installation
    ```
    # with npm
    $ npm install -g pnpm
    
    # with homebrew
    $ brew install pnpm
    ```
3. Enable the long paths in Windows
    * Go to "Run" app and type ```regedit```
    * Navigate to ```HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem```
    * On the right search for ```LongPathsEnabled``` entry
    * Set this to ```Enabled``` or ```1```
    * Open Git Bash as an Administrator and run ```git config --system core.longpaths true```
    * In Git Bash Run ```git config core.autocrlf false```
    * FInally, in Git Bash run ```git config core.eol lf```
4. Run ```task build```

Congrats! You have just setup the JS SDK locally!!
We look forward to see your contributions!
