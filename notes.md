Stuff you should know before starting the course
-----------------------------------------------

When doing the labs, things move, things change, this is cloud. What that means is that the lab instructions will not be 100% accurate, they do work for the most part, I tested them on the week of 13th Jan 2023 all the way through. You will be expected to make a bunch of accounts and do things in a long and winding way, this is the way MS want you to do things so you see everything you can in the interfaces. You will need to click around to find things sometimes, this is just how working with so many interfaces is like in the real world.

The labs will have you create an account for a user called Holly to do most of the admin task, and some sub-admin accounts you will also use. If you find that your permissions to things you need to do are not working in the way you expeced just use the MOD administrator account. It will get you through most of the labs. 


errata found as of jan20/2023
-----------------------------

-----------------
Cant find MDM intune setting in active directory

this is becuase you have been linked to the new entra portal where microsoft have moved things around a bit. This is normal in microsoft365 land, expect things to move without warning. In entra admin centre click settings>mobility, then you will find the intune settings you need. Yes, I know it is still called Intune here and not Enpoint Mananger settings, no, I don't know why. I don't work for Microsoft I just teach it.

------------------
Lab 8 exercise 3 task 3 point 5

On the Create policy window, note the six tabs that appear at the top of the page. You are currently in the 1 - Basics tab. Enter the following information:
Name: Windows10/11Policy
Description: Windows Information Protection policy for Windows 10 and 11 computers
Enrollment state: Without Enrollment


In this block you cannot create a policy without enrolment anymore, this is feature not a bug

-------------------





tips
-----

Do not log out of MOD administrator account, open a new private window for holly, or better, use a different browser if possible


winget install
--------------
winget install

Invoke-WebRequest -Uri https://github.com/microsoft/winget-cli/releases/download/v1.3.2691/Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle -OutFile .\MicrosoftDesktopAppInstaller_8wekyb3d8bbwe.msixbundle

winget install chrome


PIM
-------

Safe attachements
-----------------

https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-attachments-about?view=o365-worldwide

Safe Links 
----------------

Safe Links is a feature in Defender for Office 365 that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations. Safe Links scanning occurs in addition to the regular anti-spam and anti-malware in inbound email messages in Exchange Online Protection (EOP). Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.

https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide


Mailbox Permission Alert
------------------------




Difference between MDM and MAM
--------------------------

The main difference between MDM and MAM is the scope of control. MDM is used to manage and secure the entire device, while MAM is used to manage and secure individual applications. MDM is used to manage the overall security of a device, while MAM is used to manage the security of a specific application.
MDM is used to enforce policies on the device, while MAM is used to enforce policies on the application. MDM is used to manage the device’s hardware and software, while MAM is used to manage the application’s data and functionality.

MDM is used to manage the device’s security, while MAM is used to manage the application’s security. MDM is used to manage the device’s user access, while MAM is used to manage the application’s user access.


Create a Mail Flow Encryption Rule using Windows PowerShell
--------------------------

Install-Module MSOnline
Connect-MsolService
Set-ExecutionPolicy unrestricted
$Cred = Get-Credential
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $Cred -Authentication Basic -AllowRedirection
Import-PSSession $Session
New-TransportRule -Name "Encrypt rule for Guest Services" -SentTo "Gservices@adatum.com" -SentToScope "NotinOrganization" -ApplyOME $true


Manage DLP Policies
-------------------
https://learn.microsoft.com/en-us/microsoft-365/compliance/dlp-learn-about-dlp?view=o365-worldwide


Azure Information Protection
----------------------------
https://learn.microsoft.com/en-us/azure/information-protection/what-is-information-protection
