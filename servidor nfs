#!/bin/bash
#
############## INSTALANDO ACTUALIZACIONES Y APPS NECESARIAS ##############################
yum install -y update
yum -y install xinetd nfs-utils nfs-utils-lib nano wget

#
############## CREANDO EL SERVIDOR  Y DESHABILITANDO SELINUX #############################

sed -i 's/SELINUX=.*/SELINUX=disabled/' /etc/sysconfig/selinux
# sh -c 'echo "/server *(async,ro,no_root_squash,insecure)" >> /etc/exports' ### DESCOMENTA SI ES SOLO LECTURA
# sh -c 'echo "/server *(async,rw,no_root_squash,insecure)" >> /etc/exports' ### DESCOMENTA SI ES LECTURA Y ESCRITURA


#
############ CREANDO CARPETAS NECESARIAS #################################################

mkdir /server

############### HABILITANDO Y DESHABILITANDO DEMONIOS ####################################

chkconfig --levels 235 nfs on
chkconfig --levels 235 xinetd on
chkconfig --levels 235 iptables off

reboot
