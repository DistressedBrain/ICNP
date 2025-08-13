# ICNP
**I**nterconnected **C**ommunication **N**etwork **P**rotocol

# 1. Introduction

# 1.1 Motivation
The ICNP is designed for the use to transmit data pacages from sources to destinations where both are end-to-end encrypted and addresses have no fixed length, but is used the IP6 address pattern and is from 0.0.1 to infinity as needed.

# 1.2 Scope
The ICNP is limited to deliver data pacages and ensure to encrypt those pacages in a algoryth that constantly changes wich should not be able to decode. The ICNP can capitalize on the services of its supporting networks to provodevarious types and qualities of service.

# 1.3 Interfaces
This protocol is called on by host-to-host protocols in an internet
environment.  This protocol calls on local network protocols to carry
the internet datagram to the next gateway or destination host.

For example, a TCP module would call on the internet module to take a
TCP segment (including the TCP header and user data) as the data
portion of an internet datagram.  The TCP module would provide the
addresses and other parameters in the internet header to the internet
module as arguments of the call.  The internet module would then
create an internet datagram and call on the local network interface to
transmit the internet datagram.

In the ARPANET case, for example, the internet module would call on a

local net module which would add the 1822 leader [2] to the internet
datagram creating an ARPANET message to transmit to the IMP.  The
ARPANET address would be derived from the internet address by the
local network interface and would be the address of some host in the
ARPANET, that host might be a gateway to other networks.
*copied from Darpa Program

# 1.4 Operation

The ICNP has 3 functions: addressing, fragmentation, and end-to-end encryption

The internet modules use the addresses carried in the internet header to transmit internet datagrams toward their destinations.
The selection of a path for transmission is called routing.

The internet modules use fields in the internet header to fragment and reassemble internet datagrams when necessary for transmission through
"small packet" networks.

The internet modules use end-to-end to encrypt and secure the pacages to avoid being intercepted or being readed when sending it to a destination from a host.

The model of operation is that an internet module resides in each host
  engaged in internet communication and in each gateway that
  interconnects networks.  These modules share common rules for
  interpreting address fields and for fragmenting and assembling
  internet datagrams.  In addition, these modules (especially in
  gateways) have procedures for making routing decisions and other
  functions.

  The internet protocol treats each internet datagram as an independent
  entity unrelated to any other internet datagram.  There are no
  connections or logical circuits (virtual or otherwise).

  The internet protocol uses four key mechanisms in providing its
  service:  Type of Service, Time to Live, Options, and Header Checksum.

  The Type of Service is used to indicate the quality of the service
  desired.  The type of service is an abstract or generalized set of
  parameters which characterize the service choices provided in the
  networks that make up the internet.  This type of service indication
  is to be used by gateways to select the actual transmission parameters
  for a particular network, the network to be used for the next hop, or
  the next gateway when routing an internet datagram.

  The Time to Live is an indication of an upper bound on the lifetime of
  an internet datagram.  It is set by the sender of the datagram and
  reduced at the points along the route where it is processed.  If the
  time to live reaches zero before the internet datagram reaches its
  destination, the internet datagram is destroyed.  The time to live can
  be thought of as a self destruct time limit.

  The Options provide for control functions needed or useful in some
  situations but unnecessary for the most common communications.  The
  options include provisions for timestamps, security, and special
  routing.

  The Header Checksum provides a verification that the information used
  in processing internet datagram has been transmitted correctly.  The
  data may contain errors.  If the header checksum fails, the internet
  datagram is discarded at once by the entity which detects the error.

  The internet protocol does not provide a reliable communication
  facility.  There are no acknowledgments either end-to-end or
  hop-by-hop.  There is no error control for data, only a header
  checksum.  There are no retransmissions.  There is no flow control.

  Errors detected may be reported via the Internet Control Message
  Protocol (ICMP) which is implemented in the internet protocol
  module.

 # 2.1 Relation to Other Protocols

 ![ICNP hierarchy](https://cdn.discordapp.com/attachments/1155913540000022570/1405230662650167408/image.png?ex=689e1289&is=689cc109&hm=1b9db1b02aa9f4f5ffb86ecc0eebc0f561330fe2d40826e23526bff393cefbab&)
