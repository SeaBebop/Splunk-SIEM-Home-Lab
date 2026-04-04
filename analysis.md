# T1059.001 TestNumber 1

<div style="display: flex; justify-content: center; margin-bottom: 1rem;">
  <img src="./assets/T1059.001%231.gif" alt="T1059.001 Test 1 Demo" style="max-width: 100%; height: auto;" />
</div>

## Description
The test injected a `cmd.exe` command, simulating attacker execution via the command-line interpreter. This mimics typical malicious activity, such as running scripts or tools to interact with the system.

## Default Response of the Client Machine
The Windows Defender detected the interaction and provided a notification of a user-inputted resolution.

---

# T1059.001 TestNumber 6

<div style="display: flex; justify-content: center; margin-bottom: 1rem;">
  <img src="./assets/T1059.001%236.gif" alt="T1059.001 Test 6 Demo" style="max-width: 100%; height: auto;" />
</div>

## Description
The test launches PowerShell, which reaches out to a remote URL and retrieves a script. The downloaded script runs automatically in the background, simulating an attacker silently pulling and executing code on the system. The command was successful in using the Client Machine's network to do its bidding.

## Default Response of the Client Machine
The Client Machine's Windows Defender was unable to detect the download of the script. Upon reboot, the activity remained undetected by Windows Defender's monitoring.

---

# T1562.001 TestNumber 1

<div style="display: flex; justify-content: center; margin-bottom: 1rem;">
  <img src="./assets/T1562.001%231.gif" alt="T1562.001 Test 1 Demo" style="max-width: 100%; height: auto;" />
</div>

## Description
This test simulates an attacker impairing a defense tool by trying to stop or disable a core security service on the system. This represents typical adversary behavior where defenses are muted or interfered with to make later actions less likely to be noticed. The activity was detected and then documented to Splunk. However, the test was unsuccessful due to Windows Defender itself.

## Default Response of the Client Machine
The Client Machine's Windows Defender not only detected the behavior of this activity but, without even requesting user permission, decided to remove the test entirely.  

<div style="display: flex; justify-content: center; margin-top: 1rem;">
  <img src="../assets/T1562.001%231Result.gif" alt="T1562.001 Test 1 Result" style="max-width: 100%; height: auto;" />
</div>
