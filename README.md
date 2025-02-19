# task1
Perform a Vulnerability Assessment of a Sample Web Application

Method-1 STEPS:

 -Go to the target website.
 -Type /idnf in URL and intercept the request in Burpsuite.
 -Send this request to intruder.
 -Go to positions tab and clear all injection point (clear $), select 'idnf' as the injection    point(add $).
 -Go to Payloads and load the CrticalFile.txt and start attack.
 -Lookout of '200' response code.
 -When you get '200' code right click and click on show response in browser.
 -Check if you got any sensitive data by reading the response. 


#Types of Critical File Vulnerabilities:

File Permissions Issues: When sensitive files or directories have improperly configured file permissions, unauthorized users or processes may access, modify, or delete them.
  Example: A configuration file containing passwords is set to be readable by all users.
  
Unsecured File Upload: Allowing users to upload files without proper validation or filtering can lead to the execution of malicious scripts, such as PHP, JavaScript, or executable files.
  Example: A web server allows users to upload files, and an attacker uploads a PHP script that exploits a flaw to execute arbitrary commands.
  
  Race Conditions: This happens when a file operation (like moving or deleting files) is performed without proper synchronization, allowing attackers to exploit the timing of the operations.
   Example: An attacker could replace a critical system file while it’s being written or read, leading to system compromise.
   
Directory Traversal: This occurs when an application improperly handles file paths, enabling an attacker to access files outside the intended directories (e.g., system files).
Example: A web app that doesn't properly sanitize user input might allow an attacker to request files from the /etc/ or /bin/ directories.

Insecure File Storage: Storing sensitive data (e.g., passwords, cryptographic keys) in plaintext or unprotected files that can be easily accessed or exfiltrated.
Example: Storing sensitive data such as credentials in an unencrypted file on the server.

Code Injection via File Processing: If an application processes files but does not properly handle or sanitize the contents, it may be vulnerable to code injection.
Example: An attacker uploads a file that contains a malicious payload (e.g., a script) that gets executed when the file is opened by the application.


#Impact of Critical File Vulnerabilities:

Data Theft or Loss: Unauthorized access to critical files can lead to theft, destruction, or alteration of sensitive data (e.g., personal information, financial records).
Privilege Escalation: Attackers may gain elevated privileges by tampering with critical system files or configurations.
Remote Code Execution: In some cases, attackers may exploit critical file vulnerabilities to execute arbitrary code, potentially gaining full control over the server or system.
Denial of Service (DoS): Critical files or services may be deleted or corrupted, causing the system or application to become unavailable.

#Mitigation Strategies:
Least Privilege: Ensure that only authorized users and processes have access to critical files. Use appropriate file permissions and ACLs (Access Control Lists).
File Validation: Implement proper checks on uploaded files (e.g., file type, size, and contents) to prevent malicious uploads.
Encryption: Store sensitive data in an encrypted format both in transit and at rest to protect against unauthorized access.
Regular Patching: Keep your systems and software up-to-date with the latest security patches to avoid known vulnerabilities.
Input Sanitization: Always sanitize user inputs, especially in file paths or file upload forms, to prevent injection attacks like directory traversal.
Backup and Recovery: Regularly back up critical files and have a recovery plan in place in case of data loss or corruption.
