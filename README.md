# Failed RDP world map project



<h2>Description</h2>
The project consisted of setting up a virtual machine acting as a honey pot and using a custom powershell script to look up the attackers geolocation information and plot it on A Microsoft Sentinal map.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Microsoft Azure</b>
- <b>PowerShell</b> 
- <b>KQL</b>

<h2>Environments Used </h2>

- <b>Windows 10 pro virtual machine</b>
- <b>Microsoft Sentinal</b>

<h2>Project overview:</h2>

<p align="center">
Login to microsoft azure and create a virtual machine: <br/>
<img src="https://i.imgur.com/aar50dD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a log analytics workspace:  <br/>
<img src="https://i.imgur.com/oU2tyLt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configure the defender and data collection plans : <br/>
<img src="https://i.imgur.com/z2fTCgC.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/04ifO61.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Connect the log analytics workspace to the virtual machine:  <br/>
<img src="https://i.imgur.com/ksFJYF4.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />Setup Microsoft Sentinal:  <br/>
<img src="https://i.imgur.com/frS2v40.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the virtual machine with remote desktop and copy the public ip from the virtual machine overview:  <br/>
<img src="https://i.imgur.com/gDpONpR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FIHwNHO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/n55WxrV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
open Windows Powershell ISE and use this script (https://github.com/joshmadakor1/Sentinel-Lab/blob/main/Custom_Security_Log_Exporter.ps1) credit to josh madakor for the script:  <br/>
<img src="https://i.imgur.com/FkXGLXN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/pxpGtTc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
Make an account on (https://ipgeolocation.io/) and copy the API key then paste the API key into the section "$API_KEY":  <br/>
<img src="https://i.imgur.com/WT53B2u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/KcC0DjN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
Disable Windows Defender Firewall in the virtual machine to allow attacks:  <br/>
<img src="https://i.imgur.com/yHUV9Bp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
Create a custom log in the analytics workspace to bring in customs logs from the vm:  <br/>
<img src="https://i.imgur.com/IK8uLFM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
Go to the Log analytics workspace and use this query (https://i.imgur.com/J87ZG8q.png) to get the location data of attackers:  <br/>
<img src="https://i.imgur.com/02OsI03.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
Go to microsoft Sentinal, click on the workbooks tab, and create a new workbook then use this script (https://i.imgur.com/y0DzPRk.png) to plot the attack data:  <br/>
<img src="https://i.imgur.com/sGt3GKi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
After that you can change the visualization to a map and you shoudl get somthing that looks like this:  <br/>
<img src="https://i.imgur.com/QgoR6SS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
After waiting a while your map might look something like this:  <br/>
<img src="https://i.imgur.com/GaVgsln.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
