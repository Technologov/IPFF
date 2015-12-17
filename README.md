# IPFF
Internet Protocol - Five Fields.
An attempts to build a hybrid between IPv4 and IPv6, improving on both. Large address space, but readable addresses.

   IP version 5 "Five Fields" (IP-FF) is a new version of the Internet
   Protocol, designed as the successor to IP version 4 (IPv4) [RFC-791] 
   and IP version 6 [RFC-2460], combining many features of both,
   removing unnecessary and adding new, and optimizing the old. 
   A hybrid between the two, plus plus.

   The changes from IPv4 to IPFF fall primarily into the following
   categories:

      o  Expanded Addressing Capabilities

         IPFF increases the IP address size from 32 bits to 50 bits, to
         support more levels of addressing hierarchy, a much greater
         number of addressable nodes, yet keeping the familiar way.
         That over 230,000x times more than in IPv4 and should be enough
         for the next several hundred years or so...
         So even if humanity grows to 100 billion people in few hundred
         years from now, each can have 10,000 devices, before we deplete
         our address space.

      o  Header Format Simplification

         Some IPv4 header fields have been dropped or made optional, to
         reduce the common-case processing cost of packet handling and
         to limit the bandwidth cost of the IPFF header. Derived from 
         IPv6. IPFF goes even further by eliminating "Fragmentation",
         which improves NAT-router processing speeds, and simplifies 
         implementations.

      o  Improved Support for Extensions and Options

         Changes in the way IP header options are encoded allows for
         more efficient forwarding, less stringent limits on the length
         of options, and greater flexibility for introducing new options
         in the future. Derived from IPv6.

      o  Virtual Router Forwarding (VRF) / Layer 3 VPN extension

      o  Mobile IP problem has an order of magnitude simpler solution;
         see [Mobile TCP]

   Dropped features, compared to IPv4:

      o  Address Resolution Protocol (ARP) now became Link Address 
         Resolution Algorithm (LARA). It is now computed on the CPU.

      o  Fragmentation, as it was proven (in IPv6) that it is cheaper to
         do an MTU discovery, rather than fragment packets on each hop.
         Hosts should use either MTU path discovery or fallback to 1280
         MTU. In IPFF, fragmentation is completely eliminated.
         This increases router processing speed and NAT performance,
         and simplifies TCP/IP stack.

      o  IP Header checksums, as it was proven (in IPv6), that upper 
         layer protocols can handle it checksums and compute them 
         end-to-end, rather than hop-by-hop. This increases router 
         processing speed.

      o  Classes / classful networks.

      o  Broadcasts. Multicasts are effectively more efficient versions
         of those, just filtered at a different layer.

      o  Internet Group Management Protocol, is now optional.

   The changes from IPv6 to IPFF fall primarily into the following
   categories:

      o  Human readable, simple addressing, similar to IPv4, in 5 
         fields. 10-bits per field. 50-bit addressing.
         With 3 decimal digits in each field, and familiar dotted 
         decimal notation. examples: 10.0.0.0.1  and  382.201.769.25.133

      o  Easy migration from existing IPv4 networks.

      o  Improved efficiency: an IPFF packet is smaller than IPv6, at 20
         bytes, same as in IPv4, saving bandwidth compared to IPv6.

      o  Virtual Router Forwarding (VRF) / Layer 3 VPN extension

      o  Mobile IP problem has an order of magnitude simpler solution;
         see [Mobile TCP]

   Dropped features, compared to IPv6:

      o  Modularization: many components, that were the "core" of IPv6
         specification now became optional or eliminated.
         (NDP/IGMP/MLD/SLAAC/IPsec/Flow/Fragmentation/Link-Local...)

      o  Fragmentation.
         In IPFF, fragmentation is completely eliminated.
         This increases NAT performance and simplifies TCP/IP stack.
         Hosts should use either MTU path discovery or fallback to 1280
         MTU.

      o  Flow Labeling Capability is now optional extension.

      o  Link-local addresses are optional; no longer needed.

      o  Neighbor Discovery Protocol (NDP), divided into Link Address 
         Resolution Algorithm (LARA), and optional extensions.

      o  Stateless Auto-address configuration (SLAAC) is now optional. 
         Similar functionality should be provided by DHCPv5 or other 
         services.

      o  Internet Group Management Protocol,(IPv6 MLD) is now optional.

   Other important changes in the IPFF stack, vs both IPv4 and IPv6:

      o  In UDPv5 removed "Length" field in order to reduce overhead.

      o  DNSv5 defines a new "AA" record type.

      o  New Mode: "Silent Multicast Listeners", which combines some of
         the benefits of multicasts and some of the benefits of 
         broadcasts. In this mode, Multicast listener accepts only 
         traffic targeted at his IP & Layer 2 address, but does not 
         advertise over IGMP. In this new multicast mode, IGMP protocol
         is not needed.
         Details in [IPFF-ADDRARCH]

