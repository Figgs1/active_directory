# AD GPO Templates Providing Ransomware Protection

According to the acclaimed wikipedia.com, Pass the Hash is a hacking technique that allows an attacker to authenticate to a remote server or service by using the underlying NTLM or LanMan hash of a user's password, instead of requiring the associated plaintext password as is normally the case.


## Ransomware Programmatic Block GPO:
Allow users to select new CA
Require CA to be AD integrated (Requires Enterprise Admin access to stand up AD PKI)
Enable software restriction policies on the following file types (Applies to “All Users”):
          ADE ADE File
          ADP ADP File
          BAS BAS File
          BAT Windows Batch File
          CHM Compiled HTML Help file
          CMD Windows Command Script
          COM MS-DOS Application
          CPL Control panel item
          CRT Security Certificate
          EXE Application
          HLP Help file
          HTA HTML Application
          INF Setup Information
          INS INS File
          ISP ISP File
          LNK Shortcut
          MDB MDB File
          MDE MDE File
          MSC Microsoft Common Console Document
          MSI Windows Installer Package
          MSP Windows Installer Patch
          MST MST File
          OCX ActiveX control
          PCD PCD File
          PIF Shortcut to MS-DOS Program
          REG Registration Entries
          SCR Screen saver
          SHS SHS File
          URL Internet Shortcut
          VB VB File
          WSC Windows Script Component

# Disallow users to run applications from the following directory paths:
          %AppData%\*.exe
          %AppData%\*\*.exe
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRoot%
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\ProgramFilesDir%
          %LocalAppData%\*.exe
          %LocalAppData%\*\*.exe
          %Temp%\*.zip\*.exe
          %Temp%\7z*\*.exe
          %Temp%\Rar*\*.exe
          %Temp%\wz*\*.exe
          %UserProfile%\Local Settings\*.exe
          %UserProfile%\Local Settings\*\*.exe

## Ransomware Win10 GPO:
Allow users to select new CA
Require CA to be AD integrated (Requires Enterprise Admin access to stand up AD PKI)
Enable software restriction policies on the following file types (Applies to “All Users”):
          ADE ADE File
          ADP ADP File
          BAS BAS File
          BAT Windows Batch File
          CHM Compiled HTML Help file
          CMD Windows Command Script
          COM MS-DOS Application
          CPL Control panel item
          CRT Security Certificate
          EXE Application
          HLP Help file
          HTA HTML Application
          INF Setup Information
          INS INS File
          ISP ISP File
          LNK Shortcut
          MDB MDB File
          MDE MDE File
          MSC Microsoft Common Console Document
          MSI Windows Installer Package
          MSP Windows Installer Patch
          MST MST File
          OCX ActiveX control
          PCD PCD File
          PIF Shortcut to MS-DOS Program
          REG Registration Entries
          SCR Screen saver
          SHS SHS File
          URL Internet Shortcut
          VB VB File
          WSC Windows Script Component

# Disallow users to run applications from the following directory paths:
          %AppData%\*.exe
          %AppData%\*\*.exe
          %AppData%\*\*.exe
          %AppData%\Temp\*.zip\*.exe
          %AppData%\Temp\7z*\*.exe
          %AppData%\Temp\Rar*\*.exe
          %AppData%\Temp\wz*\*.exe
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRoot%
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\ProgramFilesDir%

## Ransomware_Win7-8 GPO:
Allow users to select new CA
Require CA to be AD integrated (Requires Enterprise Admin access to stand up AD PKI)
Enable software restriction policies on the following file types (Applies to “All Users”):
          ADE ADE File
          ADP ADP File
          BAS BAS File
          BAT Windows Batch File
          CHM Compiled HTML Help file
          CMD Windows Command Script
          COM MS-DOS Application
          CPL Control panel item
          CRT Security Certificate
          EXE Application
          HLP Help file
          HTA HTML Application
          INF Setup Information
          INS INS File
          ISP ISP File
          LNK Shortcut
          MDB MDB File
          MDE MDE File
          MSC Microsoft Common Console Document
          MSI Windows Installer Package
          MSP Windows Installer Patch
          MST MST File
          OCX ActiveX control
          PCD PCD File
          PIF Shortcut to MS-DOS Program
          REG Registration Entries
          SCR Screen saver
          SHS SHS File
          URL Internet Shortcut
          VB VB File
          WSC Windows Script Component

# Disallow users to run applications from the following directory paths:
          %AppData%\*.exe
          %AppData%\*\*.exe
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SystemRoot%
          %HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\ProgramFilesDir%
          %localAppData%\*.exe
          %localAppData%\*\*.exe
          %LocalAppData%\*\*.exe
          %LocalAppData%\Temp\*.zip\*.exe
          %LocalAppData%\Temp\7z*\*.exe
          %LocalAppData%\Temp\Rar*\*.exe
          %LocalAppData%\Temp\wz*\*.exe
