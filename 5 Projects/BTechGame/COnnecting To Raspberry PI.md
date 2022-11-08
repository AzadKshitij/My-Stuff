
IP Name = raspberrypi.mshome.net
IP = 192.168.137.228; 192.168.43.119
pass = raspberry
_**list volume  
select volume X ("X" means the volume number of the RAW drive)  
format fs=ntfs quick (or format fs=fat32 quick)  
exit**

### Steps
1. cd BTP...
2. pyenv global 3.7.12
3. source env/bin/actiate
4. python server.py
5. 