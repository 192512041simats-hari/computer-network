Portfolio Assessment

Title:

Proposing a Zero Trust Architecture for an Enterprise Network

1. Introduction:

Zero Trust is a modern cybersecurity approach based on the principle “Never Trust, Always Verify.” Unlike traditional networks, it does not automatically trust users or devices inside the organization. Every access request is verified based on identity, device security, permissions and risk.

2. Objectives:

- Protect enterprise data and applications.
- Verify every user and device.
- Implement Multi-Factor Authentication (MFA).
- Apply least-privilege access.
- Prevent unauthorized network movement.
- Continuously monitor network activities.

3. Proposed Architecture:

                    INTERNET
                        |
                   +---------+
                   | Firewall|
                   +----+----+
                        |
                  +-----+-----+
                  |    ZTNA   |
                  +-----+-----+
                        |
              +---------+---------+
              |                   |
          IAM + MFA          Device Check
              |                   |
              +---------+---------+
                        |
                  Policy Engine
                        |
                Policy Enforcement
                        |
          +-------------+-------------+
          |             |             |
       Users         Servers          IoT
       Network       Network         Network
          |             |             |
          +-------------+-------------+
                        |
                      SIEM
                        |
                       SOC

4. Main Security Components:

The proposed Zero Trust Architecture uses several security components to protect users, devices, applications and enterprise data. Each component performs a specific security function.

1. Identity and Access Management (IAM):

IAM manages user identities and controls access to enterprise resources. It ensures that only authorized users can access the required applications.

2. Multi-Factor Authentication (MFA):

MFA provides an additional layer of security by requiring users to provide more than one authentication factor before access is granted.

3. Zero Trust Network Access (ZTNA):

ZTNA provides secure access to specific applications instead of giving users complete access to the internal network.

4. Firewall:

The firewall monitors and filters network traffic. It blocks unauthorized connections and helps protect the enterprise network from external threats.

5. Network Access Control (NAC):

NAC checks the identity and security condition of devices before allowing them to connect to the enterprise network.

6. Network Segmentation:

Network segmentation separates users, servers, databases and IoT devices into different network sections. This helps reduce unauthorized access and limits lateral movement.

7. Security Information and Event Management (SIEM):

SIEM collects security logs from different systems and analyzes them to identify suspicious activities and possible security incidents.

8. Endpoint Detection and Response (EDR):

EDR continuously monitors computers and other endpoint devices. It helps detect, investigate and respond to malware and other endpoint threats.
   

6. Security Policies:

Identity Policy: Every user must have a unique account and authenticate before accessing resources.

MFA Policy: MFA is mandatory for remote users and administrators.

Least-Privilege Policy: Users receive only the permissions required for their job.

Device Policy: Only registered and secure devices can access enterprise resources.

Network Policy: Critical serve rs, databases and IoT devices must be separated into different network segments.

Monitoring Policy: Login attempts, sensitive-data access and suspicious activities must be continuously monitored.

6. Implementation Strategy:

Phase 1 – Identify: Identify users, devices, applications and sensitive data.

Phase 2 – Authenticate: Implement IAM, MFA and role-based access control.

Phase 3 – Secure Devices: Deploy endpoint security and device compliance checking.

Phase 4 – Segment Network: Separate users, servers, databases and IoT devices.

Phase 5 – Deploy ZTNA: Provide secure access to specific applications instead of the entire network.

Phase 6 – Monitor: Implement SIEM and continuous security monitoring.

Phase 7 – Test: Perform security testing and improve policies.

7. Expected Benefits:

- Reduced unauthorized access.
- Better protection against stolen credentials.
- Reduced lateral movement.
- Secure remote access.
- Improved IoT protection.
- Continuous security visibility.
- Faster threat detection and response.

8. Conclusion:

The proposed Zero Trust Architecture provides stronger security for a modern enterprise network. By continuously verifying users and devices, applying least privilege, segmenting the network and monitoring activities, the organization can reduce cyber risks while securely supporting employees, applications, servers and IoT devices.
