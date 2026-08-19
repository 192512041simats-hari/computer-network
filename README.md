CO4_AT2:Portfolio Assessment:

Title:Zero Trust Architecture for an Enterprise Network

What I looked at the Network:

For this portfolio, I prepared a Zero Trust Architecture for a typical enterprise network. I considered an organization with HR, Finance, R&D and IT departments, employee PCs, internal servers, a firewall and VPN access for employees working remotely.

While analysing this network, I mainly looked at how users and devices get access to internal resources. I understood that having a firewall and VPN is not enough by itself. Once a user enters the network, they should not automatically be trusted with everything inside it.

This is where I considered the Zero Trust approach. The basic idea I followed is “never trust automatically, always verify.” Access should depend on the user, device, resource and security conditions.

Problems in the Existing Network:

The first problem I found is too much trust after entering the network. If an employee connects to the company network, they may be able to reach resources that are not actually needed for their work. Being inside the network should not mean that everything is available.

I also considered the problem of stolen passwords and accounts. If an attacker gets an employee's password, they could try to use that account to enter the internal network. A password alone cannot prove that the person using it is really the employee.

Another problem is unnecessary permissions. For example, an HR employee may need HR applications and employee records, but there is no reason for that employee to automatically access Finance databases or R&D systems. Giving extra permissions creates more risk if the account is compromised.

I also found the risk of lateral movement. If one employee PC is infected with malware, an attacker may try to move from that PC to another computer or internal server. If departments are not properly separated, one compromised device could create a bigger security problem.

There can also be insecure or outdated devices. Even when the username and password are correct, the device itself may have outdated software or missing security updates. I considered this important because a trusted user using an unsafe device can still create a security risk.

The final problem I considered is lack of monitoring. If the organization does not properly monitor logins, access attempts and unusual activity, it becomes difficult to identify an attack early.

Security Changes I Would Make:

Based on these problems, I would change the network towards a Zero Trust model. I would focus on a few important security controls:

- MFA: I would add multi-factor authentication so a stolen password alone is not enough to access important resources.
- Least privilege: I would give users only the permissions required for their job.
- Network segmentation: I would separate HR, Finance, R&D and IT resources so users cannot freely move between departments.
- Device security checks: I would check whether a device is properly updated and has the required security protection before allowing access.
- Monitoring: I would monitor login attempts, resource access and unusual activities to identify possible attacks.

I would use these controls together because depending on only one control would leave other weaknesses.

My Zero Trust Implementation Approach:

I would not try to change the whole enterprise network immediately. I would move towards Zero Trust step by step.

First, I would identify users, devices and resources. I would list the employee accounts, PCs, servers, applications and important data. I would also identify which department needs access to each resource.

Next, I would improve authentication and permissions. I would introduce MFA for important accounts and remote VPN access. I would also remove permissions that users do not actually need.

For example, an HR employee should be able to access HR systems, but should not automatically get access to Finance or R&D systems. Similarly, an R&D employee should not automatically be able to access HR records.

After that, I would restrict unnecessary access. I would use network segmentation and access rules to separate departments and protect important servers. If one PC is compromised, the attacker should not be able to easily reach the whole network.

Then, I would add device security checks. Before giving access to important resources, I would check whether the device meets the required security conditions. An unsafe or outdated device could be given limited access until it is secured.

Finally, I would improve monitoring. I would monitor successful and failed logins, access to important resources and unusual activity. This would help the security team notice suspicious behaviour more quickly.

The firewall and VPN would still be used, but I would not treat them as the complete Zero Trust solution. VPN access should also require proper user and device verification instead of trusting the user simply because they connected through the VPN.

Reason for Choosing Zero Trust:

From looking at this network, I understood that the main problem is trust inside the network. A user being connected to the company network does not automatically mean that the user should have access to every internal system.

For example, if an employee password is stolen, MFA gives another security check. If the employee's device is also compromised, device security checks can provide another control. If the attacker still gets some access, least privilege and network segmentation can reduce the number of systems they can reach.

This is also important between departments. HR, Finance, R&D and IT have different responsibilities and data. There is no reason for every employee to have the same level of access.

So, I considered Zero Trust suitable because it reduces unnecessary trust and makes access more controlled.

My Conclusion:

While preparing this portfolio, I understood that Zero Trust is not just MFA or a single security product. It is a different approach to deciding access.

The main thing I understood is that users and devices should be checked before they are given access to resources, and access should be limited to what is actually required.

If I were moving this network towards Zero Trust, I would start by identifying users, devices and resources. Then I would improve authentication and permissions, restrict unnecessary access, add device checks and improve monitoring.

Overall, my understanding is simple: being inside the network should not automatically make someone trusted. Access should be given based on need and verified conditions.

References:

- NIST, SP 800-207: Zero Trust Architecture, National Institute of Standards and Technology.
- NIST, Cybersecurity Framework (CSF), National Institute of Standards and Technology.
- CISA, Zero Trust Maturity Model, Cybersecurity and Infrastructure Security Agency.
