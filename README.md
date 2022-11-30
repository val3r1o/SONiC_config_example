# SONiC 4.0.x </br> (Dell Enterprise SONiC) </br>
Test configuration follow best practice </br>

# note: DCI still on going

# ACCESS
Switch pair with MCLAG </br>
LAG ports for vServer attached trunk ports </br>
LAG 2x1 links on Leaf1-pair </br>

# FABRIC
2X Datacenters room (5-stage clos EVPN Fabric) </br>
L3 Fabric with BGP unnumbered </br>
Super-Spine (L3/unnumbered) connection for DC1-DC2 </br>
VxLAN/EVPN overlay (Symetric IRB) - single CP for DC1/DC2 </br>
2x TENANTS, multiple VNI </br>
Edge Leaf with BGP peering "outside" the fabric for Route type-5 </br>
BFD enable (on Leaf1/Spines-only, to save CPU) </br>
MTU aligned to 9216 all-over-the fabric and hosts </br>

# EDGE-ROUTING
L3 interface towards external router for different VRF for route type 5 termination </br>
L3 VLAN interface for external BGP peering used to "emulate" NSX-T type of attach </br>

![Fabric](https://user-images.githubusercontent.com/20860769/204854875-4a82f925-241a-43ed-913f-43d617a11bee.png)
