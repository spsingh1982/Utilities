# Rootkit Hunter

http://rkhunter.sourceforge.net/

- Download
```
wget https://sourceforge.net/projects/rkhunter/files/latest/download
```
- Extract
```
tar -xvf <>.tar.gz
```
- Install
```
./installer.sh --install
```
- Update
```
rkhunter --update
rkhunter --propupd
```
- Scan
```
rkhunter -c -sk
``` 
- Logs 
```
/var/log/rkhunter.log
```
- Automatic Scanning & Emailing
```
vi /etc/cron.daily/rkhunter.sh
chmod 755 /etc/cron.daily/rkhunter.sh
#!bin/sh
(
/usr/local/bin/rkhunter --versioncheck
/usr/local/bin/rkhunter --update
/usr/local/bin/rkhunter --versioncheck --cronjob --report-warnings-only
) | /bin/mail/ -s 'rkhunter Daily Run (R2 Tampa Tower)' sunny.singh!@verizonwireless.com
```
