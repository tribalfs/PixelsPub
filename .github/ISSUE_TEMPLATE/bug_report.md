---
name: Bug report
about: Create a report to help us improve
title: ''
labels: ''
assignees: ''

---

**Describe the bug**
A clear and concise description of what the bug is.



**Smartphone (please complete the following information):**
 - Device: [e.g. Galaxy S22Ultra]
 - OS: [e.g. Android13 OneUI4.0]

**Are you able to complete the ADB procedures?** 


**Are you able to click the apply button?** 


**Error prompted by the app, if any** 


**Screen Recording or Screenshots**
If applicable, add link to screen recording or screenshots to help explain your problem.



**Additional context**
Add any other context about the problem here.

**If the app crashes on your device**
Please provide a logcat following this procedure:
Execute the following adb command.  Do this right after the crash (device must not be rebooted yet):
`adb logcat -b crash > crashlog.txt`
_Ctrl+C_ after ~5seconds.
Then locate _crashlog.txt_ file in your adb installation folder then send it us.
