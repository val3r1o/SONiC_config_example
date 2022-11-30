SONiC (Dell Enterprise SONiC) 4.0.x test configuration (best practice)

ACCESS
Switch pair with MCLAG
LAG ports for vServer attached trunk ports
LAG 2x1 links on Leaf1-pair

FABRIC
2X Datacenters room (5-stage clos EVPN Fabric)
L3 Fabric with BGP unnumbered
Super-Spine (L3/unnumbered) connection for DC1-DC2
VxLAN/EVPN overlay (Symetric IRB) - single CP for DC1/DC2
2x TENANTS, multiple VNI
Edge Leaf with BGP peering "outside" the fabric for Route type-5
BFD enable (on Leaf1/Spines-only, to save CPU)
MTU aligned to 9216 all-over-the fabric and hosts

EDGE-ROUTING
L3 interface towards external router for different VRF for route type 5 termination
L3 VLAN interface for external BGP peering used to "emulate" NSX-T type of attach

![Fabric](https://user-images.githubusercontent.com/20860769/204854875-4a82f925-241a-43ed-913f-43d617a11bee.png)
