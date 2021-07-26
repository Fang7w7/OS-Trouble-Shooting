you need to set the invironment variable for the java first 
save it as .bat file

````

@echo off

java.exe --illegal-access=permit -javaagent:F:\softwares\burpsuite_pro_2020.7\BurpSuiteLoader_v2020.7.jar -noverify -jar F:\softwares\burpsuite_pro_2020.7\burpsuite_pro_v2020.7.jar

````