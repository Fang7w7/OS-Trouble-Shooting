save as file.vbs

````
Set oShell = CreateObject ("Wscript.Shell") 
Dim strArgs
strArgs = "cmd /c <filename>.bat"
oShell.Run strArgs, 0, false

````
