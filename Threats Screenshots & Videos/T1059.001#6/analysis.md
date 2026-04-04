
# T1059.001 TestNumber 6

  <img src="../../assets/T1059.001%236.gif" />

## Description
The test launches PowerShell, which reaches out to a remote URL and retrieves a script. The downloaded script runs automatically in the background, simulating an attacker silently pulling and executing code on the system. The command was successful in using Client Machine network configurations to do its bidding.
## Default Response of the Client Machine
The Client Machine's Window Defender was unable to detect the download of the script. Upon reboot the activity remained undetected by the Window Defender's monitoring.
