# FTP
```
apt install vsftpd
systemctl status vsftpd
nano /etc/vsftpd.conf
 - uncomment write-enable=YES
 - change the crt and key
```
If you want the FTP Insecure do this
```
in the nano /etc/vsftpd.conf an the end add:
pasv_enable=YES
pasv_min_port=(port1)
pasv_max_port=(port2)
```
FTP Explicit
```
in the nano /etc/vsftpd.conf an the end add:
pasv_enable=YES
pasv_min_port=(port1)
pasv_max_port=(port2)

allow_anon_ssl=NO
force_local_data_ssl=YES
force_local_logins_ssl=YES
ssl_tlsv1=YES
ssl_sslv2=NO
ssl_sslv3=NO
require_ssl_reuse=NO
ssl_ciphers=HIGH
```
FTP Implicit
```
in the nano /etc/vsftpd.conf an the end add:
pasv_enable=YES
pasv_min_port=(port1)
pasv_max_port=(port2)

allow_anon_ssl=NO
force_local_data_ssl=YES
force_local_logins_ssl=YES
ssl_tlsv1=YES
ssl_sslv2=NO
ssl_sslv3=NO
require_ssl_reuse=NO
ssl_ciphers=HIGH

implicit_ssl=YES
listen_port=990
```
At the end do 
`systemctl restart vsftpd`
