# pegasus-ios-detect
Commands to detect pegasus malware
##before detecting
 - iPhone backup into Mac
 - password for iPhone backup

## Shell commands

```console
brew install python3 libusb sqlite3

export PATH=$PATH:~/.local/bin


cd baseHomeDir
python3 -m venv env
source env/bin/activate


git clone https://github.com/mvt-project/mvt.git
cd mvt
pip3 install .


mkdir backup
mkdir decripted
mkdir output


curl https://raw.githubusercontent.com/AmnestyTech/investigations/master/2021-07-18_nso/pegasus.stix2 > pegasus.stix2
mvt-ios decrypt-backup -p password -d <decrypted> <backup>
mvt-ios check-backup -o <output> -i pegasus.stix2 <backup>

#check files in <output> 
# if see _detected suffix -> iPhone has malware

rm -rm backup decrypted 
```
**remarks will be done later!**
