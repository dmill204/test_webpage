<!DOCTYPE html>
<html>
  <head>
   <body bgcolor="white">
     
     <p style="text-align:center;"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/63/Kennesaw_State_Owls_logo.svg/800px-Kennesaw_State_Owls_logo.svg.png"style="width 100px;height:100px" alt="Logo"> </p>
     <hr>
    
    
    
     <html>
<head>
<style>
h1 {
  font-size: 40px;
}
</style>
</head>
<body>
  
     
        <h1> IT Capstone Project Fall 2022 CyberSecurity Team 2</h1>
  <hr>
 
         
              <a href="index.html">
                <button class = "M">Overview</button>
             </a>
             <a href="milestone1.html">
                <button class = "F">Milestone 1 </button>
             </a> 
             <a href="mile2.html">
                <button class = "R">Milestone 2</button>
             </a>
              <a href="final.html">
                <button class = "R"> Final Presentation</button>
             </a>
             <a href="resources.html">
                <button class = "R"> Resources</button>
             </a>




   
   <head>  <p style="black";> <u>Progress we have made so far.</u> </head> </p> 
The website given to us was not functioning at the beginning. Below changes had to be made to restore the website: <br>

<li>Correct the IP address information in  wp-config.php file.</li>

<li>Change “listen.acl_users = apache, nginx” to “listen.acl_users = apache” in www.conf file. </li>

<li>Fix the error in line 61 of wp-config.php, adding necessary / to comment out that line. </li>
<br>

  <img src="1.png" width="550" height="100"> 

  <br>
  <br>
  <img src="2.png" height-"100" width="550"> 
  <hr>

   <head>  <p style="black";> <u> Directory Listing.</u> </head> </p> 
  Description: Directory listing is a web application vulnerability. It occurs due to the misconfiguration of the web server. Attacker can see directory contents if it is vulnerable to directory listing. It can lead to sensitive information disclosure if sensitive information is stored & directory listing isn’t disabled.  
  <br>
<br>
Evidence: We have used a tool named “dirb” built into Kali Linux to brute-force directories. We found many directories where directory listing is enabled. Then we browsed those directories from the browser & were able to see many files including configuration file.  
  <br>
  <br>
  Mitigation: To mitigate the vulnerability, we need to turn off directory listing. As our server is apache server, we can remove the parameter ‘Indexes’ from “<Directory /var/www/html></Directory>” in the /etc/httpd/conf/httpd.conf  file to disable directory listing for specific directories. 
<br>
  <br>
Result: The directory listing is no longer accessible. 
  <br>
  <br>
  References: 
<br>
  

  
<a href="https://www.acunetix.com/blog/articles/directory-listing-information-disclosure/"> Acunetix.com</a>
<br>
<a href="https://portswigger.net/kb/issues/00600100_directory-listing/ "> Portswigger.com</a>  
<br>
<a href="https://www.kali.org/tools/dirb/ "> kali.com</a> 

  <br>
  <br>
  <img src="14.png" width="550" height="500">
  <br>
  <br>
  <img src="15.png" width="550" height="400" >
    <br>
  <br>
  <img src="16.png" width="550" height="400">
 <hr>

  <br>
  <hr>
  <head>  <p style="black";> <u> Remote Code Execution (RCE).</u> </head> </p> 
  
 Description: Remote Code Execution is a critical vulnerability. If a target is vulnerable to remote code execution, an attacker can gain shell access to the web server & execute arbitrary code in the system by exploiting the vulnerability. 
<br>
  <br>
  
Evidence: 

A tool named Metasploit built into Kali Linux was used to find the RCE vulnerability in PHP 7.2.24 version.  
  <br>
<br>

  Mitigation: It’s challenging to mitigate RCE attack. The best way to mitigate the vulnerability is to update the software & install patches regularly. The latest PHP version 8.1 can be installed to mitigate the vulnerability now. Also, zero trust policy to user inputs is another way to combat this vulnerability because unvalidated user inputs can lead to remote code execution. So impose a policy to sanitize & filter user inputs to protect the system from RCE. 

  <br>
  <br>
References: 
<br>
<a href="https://www.bugcrowd.com/glossary/remote-code-execution-rce/" >Bugcrowd.com</a>
<br>
<a href="https://www.rapid7.com/db/modules/exploit/multi/http/php_fpm_rce/">Rapid.com</a>
  <br>
<a href="https://www.comparitech.com/blog/information-security/remote-code-execution-attacks/">Comparitech.com</a>

  <br>
  <br>

 <img src="21.png" width="550" height="400">
  
  <head>  <p style="black";> <u>Password Vulnerability.</u> </head> </p> 

  <br>

  Description: Weak simple passwords and passwords from dictionary words can be retrieved easily by using Brute-force or dictionary attack.  
<br>
  <br>
Evidence: Configured MariaDB login username and password are really simple to retrieve by using Brute-force or dictionary attack. 
<br>
  <br>
Mitigation: Imposing a policy to use at least 16 characters long password consisting of upper case, lower case, numbers and symbols. 
<br>
  <br>
  
References:  
<br>
<a href="https://www.acunetix.com/blog/web-security-zone/common-password-vulnerabilities/ "> Acunetix.com</a>
  
 <hr>
  <head>  <p style="black";> Root privilege for all the users<u>.</u> </head> </p>

<br>
  Description: All the users having the admin level privilege to a system makes the system vulnerable because if an attacker gains access to a system with admin level privilege, devastating damages can be done to the system. 
<br>
  <br>
Evidence: Currently the VM does not have separate user accounts for individual users. 
<br>
  <br>
  
Mitigation: Creating separate user accounts for individual users using Principle of Least Privelege. Also switched to ssh-key authentication using RSA-2048 encryption generated by PuTTy Key Generator, and disabled ssh password authentication and disabled the root account. 

  <br>
  <br>

  References: 
<br>
<a href="https://www.protechguy.com/staff-admin-access/">Protechguy.com </a>
<br>
  
<a href="https://www.jnttek.com/no-you-cannot-have-admin-access-and-why-this-is-good-it-policy/ ">jnttek.com</a>

  <br>
  <br>
  <img src=20.png>
 <hr>
  <head>  <p style="black";> Improper host firewall configuration<u>.</u> </head></p>

  <br>
  <br>
  Description: Improper configuration of built-in host firewall allows unwanted inbound traffic which is a security threat.  
<br>
  <br>
Evidence: Command $ ufw status host revealed that the firewall was not enabled. Therefore, inbound traffic to all the Layer 4 ports was allowed. 
<br>
  <br>
Mitigation: We have enabled the firewall and created rules to allow inbound traffic to the ports that are necessary to permit accessing the server via ssh and accessing the website (22 and 80, respectively). 
  <br>
  <br>
  References:  
<br>
<a href="https://linuxconfig.org/redhat-8-stop-start-firewall#:~:text=The%20firewall%20on%20RHEL%208,onRHEL%208%20%2F%20CentOS%208%20Server./">Linux.com</a>
<br>
  
<a href="https://csguide.cs.princeton.edu/security/host/">csguide.com</a>
<br>
  
<a href="https://www.plesk.com/blog/various/linux-server-security-best-practices/"> plesk.com</a> 
<br>
  
<a href="https://www.youtube.com/watch?v=ZNmTKAdDnrc/">youtube.com</a>
<br>
  <br>
  <img src="19.png">
  <hr>
  <head>  <p style="black";> Unencrypted web traffic.</u> </head></p>
<br>

  Description: http exchanges traffic between server and the client in plain text. Therefore, if any attacker captures traffic in transit and they will be able to view all the content. 

  <br>
</br>
Evidence: Currently the web service is running on http. 
  <br>
  <br>
  Mitigation: Server and client traffic is exchanged through https in an encrypted format. Therefore, https must be used instead of http to provide security to traffic in transit.  
<br>
  <br>
References:  

<br>
<a href="https://www.plesk.com/blog/various/linux-server-security-best-practices/"> plesk.com</a> 
<br>
<a href="https://www.venafi.com/blog/what-are-differences-between-http-https-0 /">venaft.com</a>
<br>
  <a href="https://www.guru99.com/difference-http-vs-https.html/">guru.com</a> 

<br>
  <br>
  
Issue: RedHat is an Enterprise distribution of Linux and requires an account to receive updates from official repositories. 
<br>
  <br>
Mitigation: Registered an account at redhat.com and registered our server using those credentials. 

 <img src="18.png"  >
  <hr>
  <p style="text-align:center;"><img src="https://upload.wikimedia.org/wikipedia/en/7/75/Kennesaw_State_University_seal.svg"style="width 200px;height:200px" alt="Logo"></p>

  

  
   <hr>
<head>  <p style="black";> <u> Challenges and Risks   </u></head> </p> 
    
<li>There are a large number of outdated packages (over 400 security updates alone). While running updates with the command $ yum update –security, the server crashed and had to be rolled back to an earlier version. We will wait until another backup can be performed before attempting to apply security updates again. </li>

<li>Since https needs a certificate issued by Trusted Root Certification Authorities, which is expensive, we were unable to enable https instead of http to ensure encrypted data exchange. </li>

  <li>RedHat is an Enterprise distribution of Linux and requires an account to receive updates from official repositories. Registered an account at redhat.com and registered our server using those credentials</li>
  <br>
  <br>
  <img src="17.png"
  
  <hr>
  <head>  <p style="black";> <u> Plan for milestone 2   </u></head> </p> 
 <li>Apply security updates – delayed from Milestone 1 due to issues with an unregistered build of RedHat and then system crash caused by installation of updates. This step is pending a system backup. </li>

<li>Continue testing Kali Linux tools against the server and website, looking to identify vulnerabilities and apply appropriate mitigation measures </li>

<li>Ensure all packages on WordPress installation are up to date and do not contain vulnerabilities. </li>

  <hr>
  <footer align="center">
    <br>
    This is an IT Capstone project.
    <br>
    <a href="http://it5443.azurewebsites.net">Class Website</a>
    <br>
    Page Credits: Alex Thomson and Allen Thomson
</footer>

    </body>
</html>
