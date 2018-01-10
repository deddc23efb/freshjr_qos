 This script is based on FreshJR's (www.snbforums.com) work on the ASUS
 Adaptive QOS FreshJR_QOS script. This script adds user control to the
 ASUS Adaptive QOS infrastructure.

 The current script is an extension of FreshJR's original work that
 supports updated versions of ASUS router software versions 380 and beyond.

 The script is designed to run based on firewall-start events that trigger
 the script stored on standard jffs storage on a router.

 The basic function of the script is accomplished by modifying the linux
 traffic control rules (tc) setup by ASUS and the Trend Micro DPI engine.  
 
 The script addresses several deficiencies in the ASUS implementation:
   1) traffic that is unrecognized by the Trend Micro DPI is categorized
   into the Default traffic container (lowest of the low priority -
   non-configurable.) This affects many applications ... VPN, gaming,
   obfuscated traffic etc...

   2) No user configurable control over bandwidth allocation for traffic
   containers. 

   3) No facility to configure custom rules to adjust or improve traffic
   categorization in a users network.

 This script addresses all of these problems.

 Forked from FreshJR_QOS v1.92 released 09/07/2017 

 INSTALL:
   1) copy this file to /jffs/scripts/FreshJR_QOS
   2) chmod 755 /jffs/scripts/FreshJR_QOS
   3) add the following line to the end of /jffs/scripts/firewall-start
   ps w | grep -v grep | grep /jffs/scripts/FreshJR_QOS || sh /jffs/scripts/FreshJR_QOS
   4) enable Adaptive QOS (or Toggle Adaptive QoS) to trigger a script
   run.
   
 CUSTOMIZE:
   The script will by default upate the tc filters to categorize
   unidentified traffic the same as "Others" in the ASUS QOS Config UI.
   There are two additional configurations available in this script:
   1) Bandwidth Allocation per QOS Category:
      Adjust the bandwidth percentage allocation for each QOS Class below.
      Search for USER CUSTOMIZATION - BANDWIDTH ALLOCATION
   2) Upload and Download Custom traffic filter rules:
      Custom traffic filter rules for both upload and download can be
      configured (within the limits of iptables and tc.) Search for USER
      CUSTOMIZATION - UPLOAD RULES or USER CUSTOMIZATION - DOWNLOAD RULES. freshjr_qos

