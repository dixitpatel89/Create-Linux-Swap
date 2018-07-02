# Create New Linux Swap
When the swap file size is Zero, This command will help. Using this you can create swap file where needed i mostly created swap file in AWS EC2 and AWS Lightsail

### Check Swap in Linux
Check Swap size using this command

```
free -m
```

### Create a Swap in Linux

Create Swap Partition 
```
sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=2048   # for 2 GByte
sudo /sbin/mkswap /var/swap.1
sudo chmod 600 /var/swap.1
sudo /sbin/swapon /var/swap.1
```

Load Swap Partition on load
```
sudo echo '/var/swap.1 swap swap defaults 0 0' >> /etc/fstab
```
