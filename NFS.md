# nfs-server


### configuración en el servidor
```
# yum install nfs-utils
# systemctl enable --now nfs-server.service
# mkdir /storage-server
# vim /etc/export
  /storage-server   *(rw,no_root_squash)
# exportfs -rav
# exportfs -s
# showmount -e
# firewall-cmd --list-service
# firewall-cmd --add-service=nfs --permanent
# firewall-cmd --reload
# systemctl restart nfs-server.services
```

NOTA: revisar permisos en el directorio que se exporta.
 
 
### configuración en el cliente
```
# yum install nfs-utils
# systemctl enable --now nfs-server.service
# mkdir /storage-client
# vim /etc/fstab
  10.54.118.22:/storage  /storage  nfs  defaults 0 0
# systemctl daemon-reload
# mount -a
# mount | grep storage
# cd /storage
# firewall-cmd --add-service=nfs --permanent
# firewall-cmd --reload
# systemctl restart nfs-server.services
```
