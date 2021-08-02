# yum install nfs-utils
# systemctl enable --now nfs-server.service
# mkdir /storage-server
# vim /etc/export
  /storage-server   *(rw,no_root_squash)
# exportfs -s
# firewall-cmd --add-service=nfs --permanent
# firewall-cmd --reload
# systemctl restart nfs-server.service
