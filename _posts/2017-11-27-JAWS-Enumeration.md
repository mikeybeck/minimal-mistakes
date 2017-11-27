---
title: J.A.W.S. Windows Enumeration Script
layout: single
author_profile: true
read_time: true
comments: null
share: true
related: true
header: {}
---

<figure>
<a href="{{ site.url }}{{ site.baseurl }}/assets/images/JAWS.png"><img src="{{ site.url }}{{ site.baseurl }}/assets/images/JAWS.png" alt=""></a>
</figure> 
While doing my OSCP a few months ago I found I was having to  perform the same post enumeration actions on every single Windows host I compromised. I had tried a few of the existing enumeration scripts available for Windows during my lab time and found them lacking compared to the Linux versions available (Linux-Enum, PrivChecker etc).

So using the Linux versions as inspiration and in an attempt to make my PowerShell better I decided to create  [J.A.W.S. (Just Another Windows enum Script](https://github.com/411Hall/JAWS). 

JAWS is PowerShell  script designed to help penetration testers quickly identify potential privilege escalation vectors on Windows systems. It is written using PowerShell 2.0 and as such 'should' run on every Windows version since Windows 7. So far I have tested on 7, 2012 and 10 without any issues from within numerious shells, rdp sesssions etc.

Its still in the early stages and my PowerShell is weak so is far from perfect but I have successfully used on some of the HacktheBox machines to help me with privilege escalation.

**Currently Capabilities**

The script collects the following information from the host:
```
- Network Information (interfaces, arp, netstat)
- Firewall Status and Rules
- Running Processes
- Files and Folders with Full Control or Modify Access
- Mapped Drives
- Unquoted Service Paths
- Recent Documents
- System Install Files
- AlwaysInstallElevated Registry Key Check
- Stored Credentials
- Installed Applications
- Potentially Vulnerable Services
- MuiCache Files
- Scheduled Tasks
```
**Example Usage**

Video showing the script execution on the retired HacktheBox machine 'Devel' from within a Meterpreter ReverseTCP Shell. It does normally run a bit quicker but the host was being pretty laggy.

{% include video id="244633106" provider="vimeo" %}

**Example Output**

You can view the output from the retired HacktheBox machine 'Devel' on [Pastebin](https://pastebin.com/Q0Wzn74q).


Try it out now:  [https://github.com/411Hall/JAWS](https://github.com/411Hall/JAWS)