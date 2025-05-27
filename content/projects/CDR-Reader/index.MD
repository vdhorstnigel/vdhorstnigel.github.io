---
title: "CDR-Reader"
description: "A python script to parse CDR csvs from sftp directory to a database"
date: 2020-05-20
---

{{< lead >}}
This project was done before this blog and most information is from memory
{{< /lead >}}


{{< keywordList >}}
{{< keyword icon="github" >}} [Github Repo](https://github.com/vdhorstnigel/CDR-Reader) {{< /keyword >}}
{{< keyword icon = "code" >}} Python {{< /keyword >}}
{{< /keywordList >}}


I initially created this script to get the cisco call details report for a call center supervisor during my internship, its my first functional script i done for work.

I used python as the main language as I was more experienced with python, it was a very simple script just to read the file hosted in a sftp server, and taking the data from the csv file using pandas and then putting them into a mysql database

These are the fields taken from the CDR:

'globalCallID_callManagerId','globalCallID_callId','dateTimeOrigination','callingPartyNumber','originalCalledPartyNumber' 'finalCalledPartyNumber','dateTimeConnect','dateTimeDisconnect','lastRedirectDn','pkid','originalCalledPartyNumberPartition' 'callingPartyNumberPartition','finalCalledPartyNumberPartition','lastRedirectDnPartition','duration','origDeviceName' 'destDeviceName','origIpv4v6Addr','destIpv4v6Addr','originalCalledPartyPattern','finalCalledPartyPattern','huntPilotPattern' 'origDeviceType','destDeviceType'