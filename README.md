powershell -command "Get-ChildItem -Directory | ForEach-Object { '{0,10:N1} MB  {1}' -f ((Get-ChildItem $_.FullName -Recurse -ErrorAction SilentlyContinue | Measure-Object Length -Sum).Sum / 1MB), $_.Name } | Sort-Object"


del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.log
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.gz


del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.log
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.gz
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.zip

del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*
del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\tmp\*
del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\data\*




# TypeScript, HTML, JSON, SCSS files
*.ts text eol=lf
*.html text eol=lf
*.json text eol=lf
*.scss text eol=lf




Here are the most commonly used shortcut keys in IntelliJ IDEA, VS Code, and Eclipse for searching methods, classes, files, symbols, references, and navigation.


---

🔍 IntelliJ IDEA Shortcuts (Windows/Linux)

Search Anything (Universal Search)

Double Shift


Search Class

Ctrl + N


Search File

Ctrl + Shift + N


Search Symbol / Method / Variable

Ctrl + Shift + Alt + N


Find in Path (Search inside entire project)

Ctrl + Shift + F


Find in File (Search inside current file)

Ctrl + F


Go to Declaration

Ctrl + B or Ctrl + Click


Go to Implementation

Ctrl + Alt + B


Go to Method / Navigate within file

Ctrl + F12



---

🔍 VS Code Shortcuts (Windows/Linux)

Search File

Ctrl + P


Search Symbol in Workspace

Ctrl + T


Search Symbol in Current File

Ctrl + Shift + O


Search in Entire Project

Ctrl + Shift + F


Search in File

Ctrl + F


Go to Definition

F12


Go to Implementation

Ctrl + F12


Navigate Back

Alt + ←



---

🔍 Eclipse Shortcuts (Windows/Linux)

Search Type (Class Search)

Ctrl + Shift + T


Search File (Resource Search)

Ctrl + Shift + R


Search Method / Field (Workspace-wide)

Ctrl + H → Select Java Search


Quick Outline (Search Method in Current File)

Ctrl + O


Search in File

Ctrl + F


Go to Definition

F3



---

⭐ Quick Comparison Table

Action	IntelliJ IDEA	VS Code	Eclipse

Search Class	Ctrl+N	N/A (use Ctrl+T for symbol)	Ctrl+Shift+T
Search File	Ctrl+Shift+N	Ctrl+P	Ctrl+Shift+R
Search Method/Symbol	Ctrl+Shift+Alt+N	Ctrl+T / Ctrl+Shift+O	Ctrl+H
Search in Project	Ctrl+Shift+F	Ctrl+Shift+F	Ctrl+H
Search in File	Ctrl+F	Ctrl+F	Ctrl+F
Quick Outline (methods inside file)	Ctrl+F12	Ctrl+Shift+O	Ctrl+O



# Ui-Studio internal files
/webapp/config.hash.json
/webapp/generator.staged-files.json
/webapp/ui-security.json
/webapp/generator.config.json
*.generated.json
translations/*.json

