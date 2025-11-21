powershell -command "Get-ChildItem -Directory | ForEach-Object { '{0,10:N1} MB  {1}' -f ((Get-ChildItem $_.FullName -Recurse -ErrorAction SilentlyContinue | Measure-Object Length -Sum).Sum / 1MB), $_.Name } | Sort-Object"


del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.log
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.gz


del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.log
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.gz
del C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*.zip

del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\log\*
del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\tmp\*
>del /s /q  C:\Public\SOFTWARE\wildfly-15.0.1.Final\standalone\data\*

