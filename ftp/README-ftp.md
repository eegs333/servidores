sudo dnf install vsftpd
sudo systemctl enable vsftpd
firewall-cmd --add-service=ftp --perm
firewall-cmd --add-port=40000-40001/tcp --perm
firewall-cmd --reload
setsebool -P ftpd_use_passive_mode on
systemctl start vsftpd

/var/ftp
/var/ftp/pub

ftp ip-server-ftp

user:anonymous
