sudo dnf install bind bind-utils -y

sudo chgrp named -R /var/named
sudo chown -v root:named /etc/named.conf
sudo restorecon -rv /var/named
sudo restorecon /etc/named.conf

sudo firewall-cmd --add-service=dns --perm
sudo firewall-cmd --reload

sudo named-checkconf /etc/named.conf

sudo named-checkzone forward.fedora.local /var/named/forward.fedora.local
sudo named-checkzone reverse.fedora.local /var/named/reverse.fedora.local

sudo systemctl enable named
sudo systemctl start named

sudo chattr +i /etc/resolv.conf 


dig fedoramagazine.org


https://fedoramagazine.org/how-to-setup-a-dns-server-with-bind/
