# AD GPO Templates Providing Ransomware Protection

We all can agree that ransomware sucks.  With that said, there are things that you can and should be doing to harden your Windows clients and servers, which can reduce the ability of ransomware from affecting you.  Props to @thirdtier for initially creating these GPO's and continuing to expand their research and inexpensive resources.


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
