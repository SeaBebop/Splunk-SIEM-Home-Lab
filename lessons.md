# Challenges & Lessons Learned
## Time Synchronization Issues
One of the most persistent problems was a 2-hour time drift between the Windows machines and Splunk. Events appeared shifted in Splunk, making it difficult to correlate attacks with detections. <br>
Solution: <br>
I aligned all machines to Eastern Time (America/New_York). On Ubuntu I used timedatectl, and on Windows I used Set-TimeZone + w32tm /resync. After restarting Splunk, timestamps became accurate. <br>
Key Takeaway: Always verify timezones and NTP sync early. Time drift breaks correlation and makes dashboards unreliable. <br>

## Domain Join Failures on Windows 10
Even though I could ping the Domain Controller, joining the Windows 10 client to siem-lab.local kept failing with generic errors ("An Active Directory Domain Controller could not be contacted"). <br>
Solution:  Set the Preferred DNS on the internal adapter to the DC’s IP (192.168.10.9) <br>
Disabled IPv6 on the internal adapter <br>
Changed the network profile from Public to Private <br>
Disabled the firewall on the DC temporarily for testing <br>
Unchecked "User must change password at next logon" on the domain account <br>
<br>
Key Takeaway: Domain join issues in VirtualBox labs are almost always DNS or network profile related, not permissions. <br>
<br>
## Splunk Forwarder & Sysmon Configuration Issues
Inconsistent sourcetypes (xmlwineventlog vs XmlWinEventLog:Microsoft-Windows-Sysmon/Operational) <br>
Logs not appearing in the correct indexes <br>
Raw XML format instead of parsed fields <br>

Solution:  Cleaned up inputs.conf on both Windows machines with explicit sourcetype and renderXml = false <br>
Installed the official Splunk Add-on for Sysmon <br>
Created dedicated indexes (windows and windows_sysmon) <br>
Added proper props.conf for XML parsing <br>
 <br>
Key Takeaway: Forwarder configuration must be precise. Small mistakes in inputs.conf can cause major parsing and indexing problems. <br>
## Dashboard & Visualization Challenges <br>
Initial dashboards looked like plain tables instead of visual charts. <br>
Solution: <br>
Switched from stats to timechart and changed panel visualizations from Table to Column/Bar charts and Single Value panels. <br>

