# Patching-Remediation

<h2>Patch & Remediation</h2>
How to determine the best remediation approach (patching, configuration changes, or compensating controls).
Tracking and verifying remediation efforts.

<br>1. Provision a Windows VM</br>
 <br> - Disable windows firewall off ( run “wf.msc), modify NSG to allow inbound traffic</br>
 <br>
 <img src="https://imgur.com/hkN6cUc.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
<br>2. Login into the Win vm and create vulnerabilities(website Link)</br>
 <br> 
 <img src="https://imgur.com/LebEN6N.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>Install some insecure software </br>
 <br>
 <img src="https://imgur.com/3x1EIH6.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/pozZXRI.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/IUbLHtV.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br> - Enable SMB v1 </br>
 <br>
 <img src="https://imgur.com/oDJPwsW.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/maZCZKV.png"  height="600%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br> - Disable windows update
 <br>
 <img src="https://imgur.com/CHnL5un.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/RnerNQ6.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br> - Download old version of Firefox (use this link https://drive.google.com/drive/u/0/folders/1y1pSHgkpWpgDTDkYmV4bZDZtiPP6i-GA) </br>
 <br>
 <img src="https://imgur.com/eCCZ6Gf.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br> - Install old version of wireshark (keep pressing next) </br>
 <br>
 <img src="https://imgur.com/ig4OUpC.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/GZ39y8m.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 </br>
 <br> - Add guest account to Admin group </br>
 <br>
 <img src="https://imgur.com/IrL0s4P.png"  height="40%" width="40%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/gM9C5WG.png"  height="40%" width="40%" alt="Disk Sanitization Steps"/>
 </br>
 <br> - Restart the VM </br>
<br>4. Run an Advance authenticated Scan (Findings) </br>
<br>
<img src="https://imgur.com/J6eSofn.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 
<br>5. Observe Vulnerabilities/Findings </br>
 <br> - Ensure Crendentials worked in the scan</br>
  <br> 
 <img src="https://imgur.com/hJWyJOW.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>- Export Scan </br>
 <br> 
 <img src="https://imgur.com/VNQKQsv.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>6. Download powershell scripts to remediate vulnerabilities

 <h3> - Remediate Wireshark</h3>
 <br>1. Log into VM</br>
 <br>2. Uninstall Wireshark (using premade script link below)</br>
         <br>- https://github.com/joshmadakor1/lognpacific-public/tree/main/automation </br>
 <br>
 <img src="https://imgur.com/FlOgcu3.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/rq7Nfd8.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/q2bqSkW.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/X40M5LP.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>3. Restart Server</br>
 <br>4. Re-scan the VM </br>
 <br>5. Observe the findings ( wireshark shouldn't be a part of the findings due to patching/remediation)
 <br>
 <img src="https://imgur.com/4VL3XiG.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>

 <h3> - Remediating Guest account from administrator</h3>
  <br>1. Log into VM</br>
  <br>2. Remove "Guest" account from Administrator group in "computer management"</br>
  <br>
  <img src="https://imgur.com/Hv5w5Z4.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
  <img src="https://imgur.com/fRS2IPo.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
  <img src="https://imgur.com/cAycpSW.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>3. Restart Server</br>
 <br>4. Re-scan the VM</br>
 <br>5. Observe the findings( "Guest account belongs to Group" should be gone)</br>
 <br>
 <img src="https://imgur.com/MXeqfr0.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 
 <h3> - Remediate Firefox </h3>
  <br>1. Log into VM</br>
  <br>2. Remove Firefox by running a script in Powershell ISE</br>
  <br>
  <img src="https://imgur.com/QvHorCH.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
  <br>
  <img src="https://imgur.com/wA2dqkf.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>3. Restart Server</br>
 <br>4. Re-scan VM</br>
 <br>5. Observe the findings </br>
  <br>
  <img src="https://imgur.com/IOK9IhQ.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <h3> - Remediate the discourage Protocols </h3>
 <br>1. Log into VM</br>
 <br>2. Remove Cipher by running a script in Powershell ISE</br>
 <br>
 <img src="https://imgur.com/Db3htxW.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/uGwil84.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>
 <img src="https://imgur.com/eeLAb99.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>
 <br>3. Restart Server</br>
 <br>4. Re-scan the VM</br>
 <br>5. Observe the findings</br>
 <br>
 <img src="https://imgur.com/AHRuqXf.png"  height="60%" width="60%" alt="Disk Sanitization Steps"/>
 </br>

 <h3> Unpausing Windows Update</h3>
 <h3> - Remediate SMB </h3>
