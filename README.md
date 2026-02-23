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


Here are the most useful Google Chrome DevTools shortcuts (clean, practical, and actually used by developers daily):


---

🔥 Most Important DevTools Shortcuts

🗂 Open / Navigate

Action	Shortcut

Open DevTools	F12 or Ctrl + Shift + I
Open Command Palette	Ctrl + Shift + P
Open File Search	Ctrl + P
Go to Line	Ctrl + G
Go to Method / Function	@methodName (inside Ctrl + P)
Global Search (find in all files)	Ctrl + Shift + F
Search inside current file	Ctrl + F



---

🐞 Debugging

Action	Shortcut

Toggle breakpoint on current line	Ctrl + B
Step Over	F10
Step Into	F11
Step Out	Shift + F11
Resume Script Execution	F8
Pause Script	F8
Disable/Enable All Breakpoints	Ctrl + F8
Open Sources Panel	Ctrl + Shift + S



---

📄 Console

Action	Shortcut

Open Console	Esc (opens drawer)
Clear Console	Ctrl + L
Multiline Console Input	Shift + Enter
Autocomplete Suggestions	Ctrl + Space



---

🎨 Elements Panel

Action	Shortcut

Inspect Element	Ctrl + Shift + C
Edit as HTML	Enter on selected element
Expand All Nodes	Alt + Click arrow
Collapse All Nodes	Alt + Click arrow again



---

🧭 Network

Action	Shortcut

Open Network Panel	Ctrl + Shift + E
Clear Network Logs	Ctrl + R or Right-click → Clear
Filter Requests	Ctrl + F


-- Step 3: Insert Learning Paths under Synapse -> FDS
WITH base AS (
    SELECT lp_name, lp_desc
    FROM (VALUES
        ('FDS Comet Order Learning Path', 'FDS Comet Order Learning Path'),
        ('FDS IT Architecture', 'Learning path about the FDS Architecture'),
        ('Introduction to FDS IT Line', 'Introduction to FDS IT Line')
    ) AS paths(lp_name, lp_desc)
),
max_id AS (
    SELECT COALESCE(MAX(identifier_),0) AS current_max FROM learningpath_learningpath
),
numbered AS (
    SELECT 
        ROW_NUMBER() OVER () + m.current_max AS new_id,
        b.lp_name,
        b.lp_desc
    FROM base b CROSS JOIN max_id m
)
INSERT INTO learningpath_learningpath (
    identifier_,
    name_,
    description_,
    level,
    duration,
    area_identifier,
    subarea_identifier_,
    creatoruserid,
    updatoruserid,
    updatedate,
    type_,
    creationdate_,
    version_
)
SELECT
    new_id,
    lp_name,
    lp_desc,
    NULL,
    NULL,
    a.identifier_,
    s.identifier_,
    'Asif',
    'Asif',
    NOW(),
    'Learning Path',
    NOW(),
    1
FROM numbered
CROSS JOIN (SELECT identifier_ FROM learningpath_lparea WHERE name_ = 'Synapse') AS a
CROSS JOIN (SELECT identifier_ FROM learningpath_lpsubarea WHERE name_ = 'FDS') AS s;
