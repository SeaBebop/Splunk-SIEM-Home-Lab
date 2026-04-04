# Challenges & Lessons Learned
## Time Synchronization Issues
One of the most persistent problems was a 2-hour time drift between the Windows machines and Splunk. Events appeared shifted in Splunk, making it difficult to correlate attacks with detections.
Solution:
I aligned all machines to Eastern Time (America/New_York). On Ubuntu I used timedatectl, and on Windows I used Set-TimeZone + w32tm /resync. After restarting Splunk, timestamps became accurate.Key Takeaway: Always verify timezones and NTP sync early — time drift breaks correlation and makes dashboards unreliable.

## Domain Join Failures on Windows 10
Even though I could ping the Domain Controller, joining the Windows 10 client to siem-lab.local kept failing with generic errors ("An Active Directory Domain Controller could not be contacted").
Solution:  Set the Preferred DNS on the internal adapter to the DC’s IP (192.168.10.9)
Disabled IPv6 on the internal adapter
Changed the network profile from Public to Private
Disabled the firewall on the DC temporarily for testing
Unchecked "User must change password at next logon" on the domain account

Key Takeaway: Domain join issues in VirtualBox labs are almost always DNS or network profile related, not permissions.

## Splunk Forwarder & Sysmon Configuration Issues
Inconsistent sourcetypes (xmlwineventlog vs XmlWinEventLog:Microsoft-Windows-Sysmon/Operational)
Logs not appearing in the correct indexes
Raw XML format instead of parsed fields

Solution:  Cleaned up inputs.conf on both Windows machines with explicit sourcetype and renderXml = false
Installed the official Splunk Add-on for Sysmon
Created dedicated indexes (windows and windows_sysmon)
Added proper props.conf for XML parsing

Key Takeaway: Forwarder configuration must be precise. Small mistakes in inputs.conf can cause major parsing and indexing problems.
## Dashboard & Visualization Challenges
Initial dashboards looked like plain tables instead of visual charts.
Solution:
Switched from stats to timechart and changed panel visualizations from Table to Column/Bar charts and Single Value panels.

