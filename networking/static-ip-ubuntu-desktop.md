# Configure & Troubleshoot Static IP in Ubuntu Desktop

## Configure Static IP
I followed the following steps to configure a static IP address in Ubuntu Desktop:
1. In `System Settings` > `Connections`, select/create the connection and click on the `IPv4` tab.
2. Set `Method` to `Manual`, add DNS IP addresses to `DNS Servers`.
3. Click `+Add` to add a static IP.
4. In the `Address` column, enter the desired IP address.
5. In the `Netmask` column, enter the network's subnet mask. For residential networks like mine, this is `255.255.255.0`.
6. In the `Gateway` column, enter the router's private LAN IP address.
7. Disconnect & reconnect to the network.

## Troubleshoot Static IP
At this point, I was connected to the router but not the Internet. The fix:
 was to set the router's IP address as the default gateway for thenetwork interface being used:
1. Use `ip addr show` to find the name of the network interface corresponding to the IP address set in Step 4 above.
2. Set the router's IP as the default gateway for the network interface:
```
route add default gw {ROUTER-IP} {INTERFACE}
```
