CO4_AT3_Firewall-Based Access Control for a Secured Web Server

 1. Aim:

The aim of this project is to design and implement firewall rules on a Cisco
router to secure a web server setup. The rules should allow normal client
requests (HTTP/HTTPS), block unauthorized access attempts, control which
services are reachable, and then be tested against different scenarios to
prove they actually work.

 2. Network Design:

The network has two client groups (PC0/PC1 in an "unsecured" zone and
PC2/PC3 in a "secured" zone, though both are on the same subnet), connected
through switches to Router5 (Cisco 1841), which acts as the firewall. On the
other side of the router are two servers - a trusted web server that clients
are allowed to use, and an untrusted web server that represents an
unauthorized/compromised host that should be blocked.

PC0 (192.168.10.10) ──┐
                      │
PC1 (192.168.10.11) ──┤
                      ▼
                   Switch1
                      │
                      ▼
                   Switch0 ◄──────── Switch2
                      │                ▲
                      │                │
                      │          PC2 (192.168.10.12)
                      │          PC3 (192.168.10.13)
                      │
                      ▼
              Router5 / Firewall
             192.168.10.14
                      │
                      │  FIREWALL
                      │
             192.168.20.14
                      │
                      ▼
                   Switch3
                  /       \
                 /         \
                ▼           ▼
        Private Web     Public Web
           Server          Server
       192.168.20.10   192.168.20.11
  


- PC0 - 192.168.10.10
- PC1 - 192.168.10.11
- PC2 - 192.168.10.12
- PC3 - 192.168.10.13
- Router5 Gi0/0 (client side) - 192.168.10.14
- Router5 Gi0/1 (server side) - 192.168.20.14
- Private web server - 192.168.20.10
- Public web server - 192.168.20.11

Router5 sits between the client LAN (192.168.10.0/24) and the server LAN
(192.168.20.0/24), so it's the natural place to enforce the firewall rules
using an extended ACL.

 3. Firewall Rules (Extended ACL):

The idea behind the ACL is simple: only let clients talk to the Private
server on web ports, and deny everything else - especially the Public
server.


This ACL is applied inbound on Gi0/0, which is the interface facing the
clients - so unwanted traffic gets dropped as soon as it enters the router,
before it can reach the server side at all.

## 4. Testing and Results

I tested the setup in Packet Tracer's Simulation Mode by sending traffic
between the PCs and the two servers, and checked the router logs/ACL
counters afterward.

Testing and Validation
Open the private Website
From: PC0, PC1, PC2, PC3
To: 192.168.20.10
Port: 80/443
Expected: Website should load successfully.
Result: Allowed – page loaded successfully.
Access the public Web Server
From: Any PC
To: 192.168.20.11
Expected: Access should be blocked.
Result: Denied by ACL.
Test Telnet Access
From: Any PC
To: 192.168.20.10
Port: 23
Expected: Telnet access should be blocked.
Result: Denied by ACL.
Ping the private Web Server
From: Any PC
To: 192.168.20.10
Expected: Ping should receive replies.
Result: Allowed – replies received successfully.
Verify ACL Rule Hits
Device: Router5
Command: show access-lists
Expected: ACL counters should increase after the tests.
Result: Confirmed – ACL hit counters increased.

 5. Conclusion:

The ACL successfully does what it's supposed to: legitimate web traffic to
the trusted server goes through, while everything to the untrusted server
and any non-web service is blocked and logged. This confirms the design
meets the goal of permitting legitimate requests, restricting unauthorized
access, and controlling service-specific traffic.

One limitation is that a standard extended ACL is stateless by default (I
didn't use reflexive ACLs here), so it isn't tracking full connection state
the way a real stateful firewall would. A possible improvement for later
would be to use Zone-Based Policy Firewall (ZFW) or reflexive ACLs for more
realistic behavior.


