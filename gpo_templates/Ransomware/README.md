# AD GPO Templates Providing Ransomware Protection

We all can agree that ransomware sucks.  With that said, there are things that you can and should be doing to harden your Windows clients and servers, which can minimize your organization's attack surface to ransomware attacks.  Props to @thirdtier for initially creating these GPO's and continuing to expand their research and inexpensive resources.


## Ransomware GPO's provide the following benefits:

* Leverage ListCWall application to identify encrypted files on infected devices
* Restrict the directories where .exe’s can be launched from
* Implement .zip file blocks using Group Policy
* Remove local admin permission for non admin users
* Minimized mapped drives created at scale (may require creating role or function-specific logon scripts)
* Never allow drive mapping to backup destination
* Use File Server Resource Manager in Windows Server (free) to create a file screen template for cryptolocker files.  This generates an email alert whenever a cryptolocker file is seen on the file server
* Review the doc titled “Script to Deploy Group Policies”.  This automates the deployment of the cryptolocker GPO’s, deploying them to the root of the domain
* Block command and control IP ranges, country codes (such as .ru or .cn), and domains (list is included in the “Blocking at the Firewall” doc
* Block Flash, Java, and Silverlight via GPO if they are not required by the business

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
