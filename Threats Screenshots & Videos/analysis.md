
# T1562.001 TestNumber 1

  <img src="../assets/T1562.001%231.gif" />

## Description
This test simulates an attacker impairing a defense tool by trying to stop or disable a core security service on the system. This represents typical adversary behavior where defenses are muted or interfered with to make later actions less likely to be noticed. The activity was detected and then documented to splunk. However the test was unsuccessful due to Window Defender itself.
## Default Response of the Client Machine
The Client Machine's Window Defender not only detected the behavior of this activity but without even requesting the permission of the user decided to remove the test entirely. The gif below shows another attempt to use the attack, only for it to be unusable.
<img src="../assets/T1562.001%231Result.gif" />
