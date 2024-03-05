# Understanding IP Addresses

## Introduction

IP (Internet Protocol) addresses are numerical labels assigned to devices participating in a computer network that uses the Internet Protocol for communication. They serve as identifiers for devices, allowing them to send and receive data across the internet or a local network.


![image](https://github.com/Shantanu2911/Notes/assets/143939657/e4e6d94b-c7f1-4856-b728-b833e0967f1d)



## Types of IP Addresses

### IPv4 Addresses

IPv4 (Internet Protocol version 4) addresses are 32-bit numerical labels represented in the format of four decimal numbers separated by periods, such as `192.0.2.1`. Each of the four numbers can range from 0 to 255, providing a total of approximately 4.3 billion unique addresses.

However, due to the exponential growth of the internet, IPv4 addresses have become scarce, leading to the adoption of IPv6.


![image](https://github.com/Shantanu2911/Notes/assets/143939657/09300089-a124-4a67-9cc5-e520b1037968)



### IPv6 Addresses

IPv6 (Internet Protocol version 6) addresses are 128-bit numerical labels represented in hexadecimal format, separated by colons, such as `2001:0db8:85a3:0000:0000:8a2e:0370:7334`. IPv6 was introduced to address the limitations of IPv4 and to provide an exponentially larger pool of available addresses, approximately 340 undecillion (3.4×10^38).


![image](https://github.com/Shantanu2911/Notes/assets/143939657/6ba821ef-06d9-4474-a070-2298b997014c)




## IP Address Classes

IPv4 addresses are divided into five classes: A, B, C, D, and E.

- **Class A**: Reserved for very large networks, with the first octet (8 bits) indicating the network portion of the address.
- **Class B**: Reserved for medium-sized networks, with the first two octets (16 bits) indicating the network portion.
- **Class C**: Reserved for small networks, with the first three octets (24 bits) indicating the network portion.
- **Class D**: Reserved for multicast addresses, used for one-to-many communication.
- **Class E**: Reserved for experimental purposes.

## IP Address Components

### Network Portion

The network portion of an IP address identifies the network to which a device belongs. The size of this portion varies depending on the IP address class.

### Host Portion

The host portion of an IP address identifies a specific device within a network. It uniquely identifies devices on the same network.

### Subnet Mask

A subnet mask is a 32-bit number used to divide an IP address into network and host portions. It defines which portion of an IP address belongs to the network and which portion belongs to the host.

## IP Address Assignment

IP addresses can be assigned statically or dynamically:

- **Static IP Addressing**: IP addresses are manually configured and remain fixed. This method is commonly used for servers and network devices requiring permanent addresses.
- **Dynamic IP Addressing**: IP addresses are assigned automatically by a DHCP (Dynamic Host Configuration Protocol) server. This method is prevalent in home networks and enables efficient allocation of addresses.

## Conclusion

IP addresses are fundamental to the functioning of the internet and computer networks, serving as unique identifiers for devices. Understanding the types, classes, components, and assignment methods of IP addresses is essential for network administration and troubleshooting.
