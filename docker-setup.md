# Setup for OpenSuse system

To start the daemon:
- `sudo systemctl start docker`

Set Docker at boot:

- `sudo systemctl enable docker`

Add user to the docker group:

- `sudo /usr/sbin/usermod -a -G docker <username>`

If docker command does not work logout and login again from <username> or check [here](http://stackoverflow.com/q/33562109/2536357)


Set route forwarding for firewall:
When networking is handled by the Network Manager, instead of YaST you must edit the `/etc/sysconfig/SuSEfirewall2` file needs by hand to ensure the `FW_ROUTE` flag is set to yes like so:
`FW_ROUTE="yes"`

- Example of firewall configuration see [here](http://users.suse.com/~lnussel/SuSEfirewall2/EXAMPLES.html).
- Official Wiki at [here](https://en.opensuse.org/User:Tsu2/docker#Installing_Docker_on_openSUSE)
- "no outbound ports are blocked but all inbound are blocked unless pinhole port mappings are configured between the Host and Container"

Pull an image:

- `docker pull flavio/opensuse-12-3`
- `docker pull ubuntu/xenial`

List Images:
- `docker images`
- `docker search <software name>`

Interactive container:
- `docker run -i -t ubuntu:14.4 /bin/bash`

    -i: wrap STDIN of the container
    -t: allocates a pseudo-TTY or terminal and assign it to the container

- keys `Ctrl + Q` detach the TTY from the container

List running containers:
- `docker ps`
