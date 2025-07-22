##System Requirements
Please check all the systems meet the necessary requirements for kubeadm installation and correct provisioning. Check out the [Before you Begin](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#before-you-begin) section.
1. To check the number of CPUs (You would need **two or more**)
```
t@pc:~$ nproc
8
```

2. Check RAM (You need at **least 2GB**)
```
t@master-node:~$ grep MemTotal /proc/meminfo
MemTotal:   	16254132 kB
```

3. Check **IP address for each physical machine** and keep a note as you need the private IP address of each machine (master and workers) to set up your cluster and allow communication.
```
t@pc:~$ ifconfig -a
```
  
If you're connected to the network via **Wi-Fi**, your IP will be under **wlp2s0**.
If connected via **Ethernet**, you'll see it under **enp3s0** or similar.

Make sure each device has an unique IP address. (Why)
	
4. Check OS and Kernel version
```
t@pc:~$ lsb_release -a             	
Distributor ID:	Linuxmint
Description:	Linux Mint 22.1
Release:	22.1
Codename:	xia

t@master-node:~$ uname -r
6.8.0-58-generic
```

5. To check your glibc version:
```
t@pc:~$ ldd --version
ldd (Ubuntu GLIBC 2.39-0ubuntu8.4) 2.39
```

