### 1. How many users and groups?
```sh
rip.pl -r "/home/sansforensics/P3/Win10 Registry Artifacts/SAM" -p samparse > Q1_2_3.txt
```

### 2. What are the names?


Users:
Administrator [500]
Guest [501]
DefaultAccount [503]
WDAGUtilityAccount [504]
aubie [1000]

Groups:
Users [3]
Backup Operators [0]
Replicator [0]
Distributed COM Users [0]
Hyper-V Administrators [0]
Access Control Assistance Operators [0]
Performance Monitor Users [0]
Cryptographic Operators [0]
Performance Log Users [0]
Network Configuration Operators [0]
Remote Desktop Users [0]
Administrators [2]
Power Users [0]
System Managed Accounts Group [1]
Event Log Readers [0]
Guests [1]
IIS_IUSRS [1]
Device Owners [0]
Remote Management Users [0]

### 3. When did the user aubie last log in to the system?
2020-10-23 00:01:01Z

### 4. What applications are automatically started when the user logs into the system and when was the last time the autostart was run?
For all users:
```sh
rip.pl -r "/home/sansforensics/P3/Win10 Registry Artifacts/software" -p run > Q_4.1.txt
```
VMware User Process - "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe" -n vmusr
VMware VM3DService Process - "C:\Windows\system32\vm3dservice.exe" -u
SecurityHealth - %windir%\system32\SecurityHealthSystray.exe

For aubie:
```sh
rip.pl -r "/home/sansforensics/P3/Win10 Registry Artifacts/Users/aubie/NTUSER.DAT" -p run > Q4.2.txt
```
OneDrive - "C:\Users\aubie\AppData\Local\Microsoft\OneDrive\OneDrive.exe" /background

### 5. What was the private IP address associated with the system?
```sh
rip.pl -r "/home/sansforensics/P3/Win10 Registry Artifacts/system" -p ips > Q_5.txt
```
192.168.48.141 

### 6. What are the most recently executed commands from the Windows Run command window?
```sh
rip.pl -r "/home/sansforensics/P3/Win10 Registry Artifacts/Users/aubie/NTUSER.DAT" -p runmru > Q_6.txt
```
The most recent commands were: cmd, "C:\Program Files\Windows Mail\wab.exe", and "C:\Program Files\internet explorer\iexplore.exe". With the iexplorer.exe being the most recent.









