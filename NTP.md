# NTP

### Configuración en el servidor
```
# yum install chrony
# vi /etc/chrony.conf
  #agregar la red permitida - para sincronizarse con este servidor
  allow 192.168.0.0/16
# firewall-cmd --add-service=ntp -permanent
# firewall-cmd --reload
# systemctl enable --now chronyd
# chronyc traking
# chronyc clients
```
### Configuración en el cliente
```
# yum install chrony
# vi /etc/chrony.conf
  #agregar el servidor y comentar la lineas que comienza con pool
  server 10.54.118.22 
# firewall-cmd --add-service=ntp -permanent
# firewall-cmd --reload
# systemctl enable --now chronyd
# chronyc traking
# chronyc sources
```
