# Infrastructure-Servers

### Installation
Install vms on ubuntu server 20. My hp elitedesk mini has 8 cpu cores. I have 3 of these so preferrably install 3 vms each of 2vcpus for each vm 

Disk size is 250G each so allocate apprx 50G per vm 
Ram of 16G each, so 2G ram each vm 

| resource | required | available |
| -------- | ---------| ----------|
| CPU      | 2 vcpu   | 8 vcpu    | 
| Ram      | 16G      | 2 G       |
| Disk     | 50G      | 250G      |


### Requirements 
| server  |  resources | purpose  |
| --------| ---------- | ---------|
| Webserver | 1        | host content |
| jenkins server | 1   | automation | 
| kubernetes master | 3 | kubernetes  master nodes |
| kubernetes workers | 3 | kubernetes  worker nodes |


### Requirements 
1. Automate server builds using ansible and kickstart 
2. Automate networking, all vms should be able to talk to every other vm 
3. Install rhel/centos vms as infrastructure vms 
4. Install ubuntu as kubernetes vms 


### Steps 
#### Manually setup Webserver 
1. Validatge virtualization support on the server. 0 means virtualization is not supported  
``` alpha@alpha:~$ egrep -c '(vmx|svm)' /proc/cpuinfo```  
```16```

2.  Update repositories  
``` sudo apt update ```

3. Install kvm packages   
```alpha@alpha:~$ sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils -y ```
