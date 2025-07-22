# load required modules
```
sudo modprobe overlay
sudo modprobe br_netfilter
```

# add persistent configuration
```
sudo tee /etc/modules-load.d/k8s.conf <<EOF
overlay
br_netfilter
EOF
```

# set required networking parameters
```
sudo tee /etc/sysctl.d/k8s.conf <<EOF
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
net.bridge.bridge-nf-call-ip6tables = 1
EOF
```

# apply the settings
```
sudo sysctl --system
```
