# Discover Ip address of host available on same network using host-name
***Avahi*** is an open-source software that implements Zeroconf networking protocols like mDNS and DNS-SD, enabling devices to automatically discover and communicate with each other on local networks without manual configuration.

##### Utilizing "avahi-resolve-host-name"
We will focus on the "avahi-resolve-host-name" command, which is a Linux command-line utility included in the Avahi software suite. This utility is used to translate a host name (a human-readable name for a networked device) into an IP address by leveraging Zeroconf networking protocols like mDNS. With this tool, users can easily identify the IP address associated with a specific host name on their local network without the need for configuring a traditional DNS server.

### Follow below steps: 👇👇👇
1. Ensure that the systems are connected to the same network and share the same IP address range.
2. Verify that the Avahi service is running on both systems. You can check the status of the Avahi service using the following command:
    ```sh
    sudo service avahi-daemon status
    ```
2. Set the hostname on the system you want to discover. Open the Avahi daemon configuration file for editing:
    ```sh
    sudo nano /etc/avahi/avahi-daemon.conf
    ```
    Find and uncomment the line #host-name=foo or change the value of <foo>, then save the file.
3. Restart the Avahi daemon service:
    ```sh
    sudo systemctl restart avahi-daemon
    ```
4. Now, use the following command to resolve the host's IP address using its hostname (the host name you set on the other system):
    ```sh
    avahi-resolve-host-name <host_name>.local
    ```
    Example:
    ```sh
    avahi-resolve-host-name foo.local
    ```
    > Note: Please remember that adding ".local" after the host name is mandatory in this command.

By following these steps, you can easily discover the IP address of a host on the same network using its hostname with the help of Avahi and the "avahi-resolve-host-name" command.


#### Linux commands
Here are some essential Avahi-related commands:
- avahi-autoipd
- avahi-publish
- avahi-resolve-address
- avahi-browse
- avahi-publish-address
- avahi-resolve-host-name
- avahi-browse-domains
- avahi-publish-service
- avahi-set-host-name
- avahi-daemon
- avahi-resolve

> Use <command> --help, to get to know more about usage.

## License
**Free Software, Hell Yeah!**

## Authors
- [Rahul Gupta](https://github.com/rahulelex)
