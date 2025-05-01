# NAT Translation and Static Routing

## Objective
Ensure all computers can access the Google server after NAT translation using static routing.

---

## Configuration Steps

1. **Assign IP addresses** to all PCs, routers, and servers according to the topology diagram.

2. **Configure VLAN interfaces** on Router0 for VLAN 10 and VLAN 20.

3. **Configure trunk ports** on the switch connected to Router0 and assign VLANs to respective switchports.

4. **Enable NAT** on Router0:
   - Define access lists for inside networks (VLAN 10 and VLAN 20).
   - Set up NAT with overloading using the public interface (GigabitEthernet0/0).
   - Mark inside and outside NAT interfaces correctly.

5. **Configure static routes**:
   - On Router0, add a static route to reach the Google server via Router1.
   - On Router1, add static routes for VLAN 10 and VLAN 20 networks to reach them via Router0.

6. **Configure IP addresses** and default gateways on all PCs:
   - PCs in VLAN 10 should use the Router0 VLAN 10 subinterface IP as gateway.
   - PCs in VLAN 20 should use the Router0 VLAN 20 subinterface IP as gateway.

7. **Verify NAT translation** and end-to-end connectivity using ping and `show ip nat translations` on Router0.

8. **Ensure connectivity** to the Google server from all PCs.

## Project Files

- `.pkt` file containing the full Packet Tracer simulation.