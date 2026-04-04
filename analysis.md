# T1059.001 TestNumber 1

  <img src="./assets/T1059.001%231.gif" />

## Description
The test injected a cmd.exe command, simulating attacker execution via the commandline interpreter. This mimics typical malicious activity, such as running scripts or tools to interact with the system.
## Default Response of the Client Machine
The Window Defender detected the interaction and provided a notification of a user inputed resolution. 


# T1059.001 TestNumber 6

  <img src="./assets/T1059.001%236.gif" />

## Description
The test launches PowerShell, which reaches out to a remote URL and retrieves a script. The downloaded script runs automatically in the background, simulating an attacker silently pulling and executing code on the system. The command was successful in using the Client Machine's network to do its bidding.
## Default Response of the Client Machine
The Client Machine's Window Defender was unable to detect the download of the script. Upon reboot the activity remained undetected by the Window Defender's monitoring.


# T1562.001 TestNumber 1

  <img src="./assets/T1562.001%231.gif" />

## Description
This test simulates an attacker impairing a defense tool by trying to stop or disable a core security service on the system. This represents typical adversary behavior where defenses are muted or interfered with to make later actions less likely to be noticed. The activity was detected and then documented to splunk. However the test was unsuccessful due to Window Defender itself.
## Default Response of the Client Machine
The Client Machine's Window Defender not only detected the behavior of this activity but without even requesting the permission of the user decided to remove the test entirely. The gif below shows another attempt to use the attack, only for it to be unusable.
<img src="./assets/T1562.001%231Result.gif" />
