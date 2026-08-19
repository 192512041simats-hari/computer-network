CO4_AT2:PORTFOLIO ASSESSMENT

TITLE:Zero Trust Architecture for an Enterprise Network.

1. Project Overview:

Introduction:

Modern enterprise networks contain employees, servers, databases, cloud applications, IoT devices, and remote users. Traditional security models often assume that users inside the organization are trustworthy.

The proposed Zero Trust Architecture (ZTA) removes this assumption and follows the principle:

«“Never Trust, Always Verify.”»

Every user, device, and access request is verified before access to enterprise resources is granted.

PROJECT GOAL:

To design a secure enterprise network using Zero Trust principles such as:

- Identity verification
- Multi-Factor Authentication (MFA)
- Least-privilege access
- Network segmentation
- Firewall policies
- Continuous monitoring

2. Problem Statement and Objectives:

Problem Statement:

An enterprise network can be exposed to:

- Stolen user credentials
- Unauthorized devices
- Malware and ransomware
- Insider threats
- Lateral movement
- Insecure remote access
- Unprotected IoT devices
- Unauthorized access to sensitive databases

A compromised device should not automatically gain access to other enterprise resources.

Objectives:

1. Verify every user before granting access.
2. Verify the security status of devices.
3. Apply least-privilege access.
4. Separate critical network resources.
5. Restrict unauthorized traffic.
6. Secure remote and guest access.
7. Monitor network activity continuously.
8. Test the effectiveness of the proposed design.

3. Proposed Enterprise Network Architecture:

The proposed network divides the enterprise into different security zones.

Network Diagram:

               USER / DEVICE
                    |
                    v
                 INTERNET
                    |
                    v
                 FIREWALL
                    |
                    v
             ZERO TRUST GATEWAY
                    |
                    v
               IDENTITY + MFA
                    |
                    v
               POLICY CHECK
                    |
                    v
               CORE SWITCH
                    |
      +----------+----------+----------+
      |          |          |          |
      v          v          v          v
    USER       SERVER     DATABASE     IoT
    VLAN 10    VLAN 20     VLAN 30    VLAN 40
      |
      v
    AUTHORIZED
    APPLICATION
  


4. Zero Trust Security Model:

The proposed architecture follows five important principles:

1. Never Trust, Always Verify:

Users and devices are not automatically trusted.

2. Least Privilege:

Users receive only the access required for their role.

3. Assume Breach:

The design assumes that an account or device may already be compromised.

4. Verify Device Health:

Device security status is checked before sensitive access.

5. Continuous Monitoring:

Access and network activity continue to be monitored after authentication.


Flowchart 1 — Zero Trust Access Process:

                  ACCESS REQUEST
                        |
                        v
               +------------------+
               | Verify Identity  |
               +--------+---------+
                        |
                  Valid User?
                   /        \
                 No          Yes
                 |            |
                 v            v
               DENY     Verify Device
                              |
                        Trusted Device?
                         /          \
                       No            Yes
                       |              |
                       v              v
                     DENY       Check User Role
                                      |
                                      v
                              Check Access 
                            Policy
                                      |
                                +-----+-----+
                                |           |
                              Allow        Deny
                                |           |
                                v           v
                         Resource Access  Block
                                |
                                v
                         Monitor Activity


5. Identity, Authentication and Device Security:

Identity is the first security layer in the proposed architecture.

Authentication Controls:

- Username and password
- Multi-Factor Authentication
- Role-Based Access Control
- Strong password policy
- Account monitoring

MFA Example:

      Username + Password
             |
             v
            MFA
             |
             v
    OTP / Authenticator
             |
             v
    Identity Verified
             |
             v
    Continue Access Check

Device Verification:

The organization should verify:

- Device registration
- Operating system updates
- Security software
- Encryption
- Device compliance
- Device identity

An unknown or compromised device should be denied or isolated.

6. Network Segmentation and Access Control:

Network segmentation prevents a compromised system from freely communicating with critical resources.


## VLAN Design

| VLAN | Network | Purpose |
|---|---|---|
| VLAN 10 | User Network | Employee PCs |
| VLAN 20 | Server Network | Application Servers |
| VLAN 30 | Database Network | Sensitive Databases |
| VLAN 40 | IoT Network | IoT Devices |
| VLAN 50 | Guest Network | Guest Internet |
| VLAN 60 | Admin Network | IT Administrators |


## Access Control Example

| Source | Destination | Access |
|---|---|---|
| Employee | Business Application | Allow |
| Employee | Database | Deny |
| Administrator | Server | Allow |
| Guest | Internet | Allow |
| Guest | Internal Network | Deny |
| IoT | Required Server | Allow |
| IoT | Database | Deny |
| Internet | Internal Network | Deny |


7. Security Policies:

The following policies are applied to the enterprise network.

Policy 1 — Authentication:

Every user must authenticate before accessing enterprise resources.

Policy 2 — MFA:

MFA is mandatory for administrators, remote users, and sensitive applications.

Policy 3 — Least Privilege:

Users receive only the permissions required for their job.

Policy 4 — Device Compliance:

Only registered and compliant devices can access protected resources.

Policy 5 — Default Deny:

Traffic that is not explicitly permitted is denied.

Policy 6 — Network Segmentation:

User, server, database, IoT, guest, and administrative networks must remain separated.

Policy 7 — Guest Access:

Guest users can access the Internet but cannot access internal enterprise resources.

Policy 8 — Monitoring:

Authentication, firewall, server, and endpoint activities must be monitored.

8. Firewall and Traffic Control:

The firewall acts as an important enforcement point between network zones.

## Firewall Rules

| No. | Source | Destination | Service | Action |
|---:|---|---|---|---|
| 1 | User VLAN | Web Server | HTTPS | ALLOW |
| 2 | User VLAN | Database | Database Port | DENY |
| 3 | Admin VLAN | Servers | Management | ALLOW |
| 4 | Guest VLAN | Internet | HTTP/HTTPS | ALLOW |
| 5 | Guest VLAN | Internal Network | Any | DENY |
| 6 | IoT VLAN | Required Server | Required Port | ALLOW |
| 7 | IoT VLAN | Database | Any | DENY |
| 8 | Internet | Internal Network | Any | DENY |



Flowchart 2 — Firewall Decision Process

              INCOMING REQUEST
                     |
                     v
             +---------------+
             | Firewall      |
             | Rule Check    |
             +-------+-------+
                     |
              Rule Exists?
                /        \
              Yes         No
               |           |
               v           v
         Check Action    DENY
            /    \
        Allow    Deny
          |        |
          v        v
       Forward   Block
          |
          v
     Log Activity

This follows the default-deny principle.

9. Implementation Strategy:

The Zero Trust architecture should be implemented gradually rather than changing the entire enterprise network at once.

Phase 1 — Identify Resources:

Identify:

- Users
- Devices
- Applications
- Servers
- Databases
- IoT devices
- Cloud services
- Sensitive information

Phase 2 — Establish Identity:

Implement centralized identity management, user roles, MFA, and authentication policies.

Phase 3 — Segment the Network:

Create VLANs for users, servers, databases, IoT, guests, and administrators.

Phase 4 — Apply Security Policies:

Configure firewall rules, access-control rules, least-privilege permissions, and device policies.

Phase 5 — Monitor:

Collect logs and monitor authentication, network traffic, devices, servers, and applications.

Phase 6 — Test and Improve:

Perform authorized and unauthorized access tests and modify policies based on the results.

---

Flowchart 3 — Implementation Strategy:

              START
                |
                v
       Identify Users & Assets
                |
                v
       Implement Identity + MFA
                |
                v
        Verify Devices
                |
                v
       Segment the Network
                |
                v
     Configure Firewall Policies
                |
                v
       Apply Least Privilege
                |
                v
       Enable Monitoring
                |
                v
       Security Testing
                |
          +-----+-----+
          |           |
       Successful   Problems
          |           |
          v           v
       Deploy      Improve
          |           |
          |___________|
                |
                v
       Continuous Monitoring
                |
                v
               END


10. Testing, Results and Conclusion:

Security Testing:

The proposed design can be evaluated using the following scenarios:

## Security Testing

| Test Case | Expected Result |
|---|---|
| Valid employee + trusted device | Access Allowed |
| Wrong password | Access Denied |
| Failed MFA | Access Denied |
| Unknown device | Access Denied |
| Guest → Internal Server | Blocked |
| Employee → Authorized Application | Allowed |
| Employee → Database | Blocked |
| Administrator → Server | Allowed |
| IoT → Unauthorized Server | Blocked |
| Suspicious login | Alert Generated |

Expected Results:

The proposed Zero Trust Architecture should:

- Reduce unauthorized access.
- Prevent unnecessary lateral movement.
- Protect sensitive databases.
- Isolate IoT and guest devices.
- Secure remote access.
- Enforce least privilege.
- Improve network visibility.
- Detect suspicious activities.

Conclusion:

The proposed Zero Trust Architecture provides a practical security model for an enterprise network. Instead of trusting users based only on their network location, every request is evaluated using identity, device status, user role, resource, and security policy.

The combination of MFA, least privilege, network segmentation, firewall controls, and continuous monitoring provides stronger protection against unauthorized access and compromised devices.

The architecture can also be implemented gradually, allowing an organization to improve security without replacing its entire existing network infrastructure.

Final Security Principle:

«Never Trust. Always Verify.»
