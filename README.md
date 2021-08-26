# meshify-rpm
Repository for RPM based linux systems

## Welcome to the Meshify Repository

You can use this repo to install the meshify-client for redhat/fedora linux distros.

```shell

# Install wireguard if not already installed
sudo yum install wireguard

# Install meshify-client
$ sudo yum-config-manager --add-repo https://meshify-app.github.io/meshify-rpm/meshify.repo
$ sudo yum install meshify

# Update the config
sudo mkdir -p /etc/meshify
sudo nano /etc/meshify/meshify-client.config.json

{
    "MeshifyHost": "https://my.meshify.app",
    "HostID": "",
    "ApiKey": ""
}
Update the HostID and ApiKey from your meshify control panel for the host.


# Enable and start the service
sudo systemctl enable meshify
sudo systemctl start meshify

# Enable IP forwarding for subnet routing or VPN tunneling
sudo nano /etc/sysctl.conf

In the file, uncomment the line below to enable IP forwarding

# Uncomment the next line to enable packet forwarding for IPv4
net.ipv4.ip_forward=1

Ctrl-X to save the file, then reboot the system.

sudo reboot now

```


