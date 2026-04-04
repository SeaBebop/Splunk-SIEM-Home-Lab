# Challenges & Lessons Learned

## Client Machine Failed to Join Domain
 <img src="./assets/pics/ErrorDomainJoin.jpg" width="400px" />
 
My client user wasn't able to connect to the domain controller with the correct log in. And the prompt gave zero clue as to why.
<img src="./assets/pics/ErrorDomainJoinClue.jpg" width="400px" />
Learned that the control panel version of troubleshooting is different from window's settings and usually provides better error messages for an apt solution. 
## Splunk Input.conf
<img src="./assets/pics/SysmonError.jpg" width="400px" />
The logs were not in CIM compliance and the source type wasn't what I set in the input.conf
<img src="./assets/pics/InputConfigError.jpg" width="400px" />
Learned a more modern approach to creating the input.conf from splunk documentation.

## Time Sync Issues
<img src="./assets/pics/TimeSyncError.jpg" width="400px" />
The server times were not only in different time zones but the DC server was drifting up and down in time. This caused splunk to recieve and document logs in incorrect times.
<img src="./assets/pics/TimeSyncFix.jpg" width="400px" />
Learned how to sync time between linux and window's machines with commandlines.
