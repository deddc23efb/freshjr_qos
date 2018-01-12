FreshJR_QOS
##FreshJR_QOS v382 released 01/10/2017
```
original reference: https://pastebin.com/5nMP45ev
```
FreshJR's Install Instructions:
```
Open putty. Hostname is router ip. Port is 22. Connection Type SSH. Click open. Type in Password.

If firewall-start is not yet properly formatted, or has never been formatted, then run the following.
The file, firewall-start, will NOT be properly formatted if you do not have any scripts installed into it.
Run this command first to properly delete/format the firewall-start file.
Code:
-----CAUTION READ NOTES-----
echo "#!/bin/sh" > /jffs/scripts/firewall-start
-----CAUTION READ NOTES-----
NOTE: This will delete firewall-start and create a new one with a proper header. Do not use if firewall start is already properly formatted and you have other scripts working.

​
When firewall-start is properly formatted then run the following commands to complete the install:

Paste these three commands, one by one, from clipboard by right clicking into putty to install the script.
Code:
echo "/jffs/scripts/FreshJR_QOS" >> /jffs/scripts/firewall-start
chmod 755 /jffs/scripts/firewall-start
chmod 755 /jffs/scripts/FreshJR_QOS
Just a linux FYI: The two echo commands used above are slightly different from each other.
Echo with > = overwrites and echo with >> = appends
```
