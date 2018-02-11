# AD GPO Template Providing Pass-the-Hash Mitigations

According to the acclaimed wikipedia.com, Pass the Hash is a hacking technique that allows an attacker to authenticate to a remote server or service by using the underlying NTLM or LanMan hash of a user's password, instead of requiring the associated plaintext password as is normally the case.

After an attacker obtains valid user name and user password hash values (somehow, using different methods and tools), they are then able to use that information to authenticate to a remote server or service using LM or NTLM authentication without the need to brute-force the hashes to obtain the cleartext password (as it was required before this technique was published). The attack exploits an implementation weakness in the authentication protocol, where password hash remain static from session to session until the password is next changed.

This technique can be performed against any server or service accepting LM or NTLM authentication, whether it runs on a machine with Windows, Unix, or any other operating system.

Cliff notes:  Its easily exploitable, and bad.

The GPO's and supporting documents and files were pulled from:https://blogs.technet.microsoft.com/secguide/2016/10/17/security-baseline-for-windows-10-v1607-anniversary-edition-and-windows-server-2016/

Also, you should deploy LAPS as additional mitigating layer:  https://www.microsoft.com/en-us/download/details.aspx?id=46899
