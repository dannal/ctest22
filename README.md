This sample template includes config for vs code to run  c/cpp project using MS C/C++ compiler.
Changes to default include compiling all cpp files in current folder and specifying an output exe name

** Must launch vs code in correct folder from the VS Developer Command prompt as it has all the paths to compiler etc configured **

Setup Steps
-----------
https://code.visualstudio.com/docs/cpp/config-msvc

1-Install C/C++ extension for VS Code
2 Create tasks.json : Terminal -> Configure Default Build Task - choose cl.exe build active file

3 Modify tasks.json 
    Modify compiler config args to compile all cpp files, not just the currently active one
        ${file} => "${workspaceFolder}\\*.c"   ** change to *.c is necessary

    Modify compiler config args to produce a certain output name
        "${fileDirname}\\${fileBasenameNoExtension}.exe"  => "${workspaceFolder}\\hello.exe",

5 Create launch.json : Run -> Add Configuration - choose C++ (Windows)
    Modify launch,json
        change program value from "${fileDirname}\\${fileBasenameNoExtension}.exe",
        to "hello.exe", or whatever

    Add a run precondition to compile project


** Must launch vs code in correct folder from the VS Developer Command prompt as it has all the paths to compiler etc configured **