# Enterprise Network Analysis and Migration to Zero Trust Architecture

## 1. Introduction

For this portfolio, I have analyzed a typical enterprise network and identified the security problems that can occur in a traditional network. Based on the analysis, I have proposed a migration towards Zero Trust Architecture (ZTA).

In a traditional enterprise network, security mainly depends on the firewall and the assumption that users inside the network can be trusted. This approach is not enough today because attackers can gain access using stolen credentials, compromised devices or malware.

Zero Trust follows the idea of **"Never Trust, Always Verify."** This means that users and devices should be verified before they are allowed to access company resources, even if they are already inside the network.

---

## 2. Existing Enterprise Network

For the analysis, I considered an enterprise with different departments such as HR, Finance, R&D and IT.

The network contains:

* Internet connection
* Firewall
* Core switches
* Department-level LANs
* Internal servers
* Employee computers
* VPN for remote employees
* Centralized user authentication

The firewall provides protection between the internet and the internal network. Employees inside the network can access the resources required for their work.

However, the internal network still has a level of implicit trust.

---

## 3. Analysis of the Existing Network

### 3.1 Excessive Internal Trust

Once a user successfully enters the internal network, the user may have access to several internal resources.

This creates a problem if an employee account is compromised. An attacker using the stolen account may be able to access resources that were not originally intended for that user.

### 3.2 Lack of Proper Segmentation

If departments are not properly separated, an attacker who compromises one computer may try to move to other systems.

For example, compromising a computer in the HR department should not provide any path to sensitive Finance or R&D systems.

### 3.3 Password Dependency

Using only usernames and passwords for authentication creates a risk if credentials are stolen through phishing or other attacks.

### 3.4 Remote Access Risk

VPN provides a secure connection to the enterprise network, but authentication through VPN alone does not guarantee that the device being used is secure.

A compromised laptop can still become a security risk after connecting to the network.

### 3.5 Excessive Permissions

Users may have more permissions than they actually require.

For example, an HR employee should not normally have access to financial databases or R&D systems.

### 3.6 Limited Continuous Monitoring

Traditional networks may focus heavily on protecting the network boundary. This can make it difficult to identify suspicious activity occurring inside the network.

---

# 4. Security Requirements

Based on the above problems, the enterprise needs a security model that can:

* Verify every user before granting access.
* Verify the device being used.
* Provide only the required permissions.
* Separate sensitive systems.
* Monitor user activity.
* Detect unusual access attempts.
* Protect remote workers.
* Reduce lateral movement after a compromise.

Zero Trust Architecture addresses these requirements.

---

# 5. Proposed Zero Trust Architecture

The proposed Zero Trust model would be based on the following principles.

## 5.1 Identity Verification

Every user should have an individual identity.

Multi-Factor Authentication should be implemented so that a password alone is not enough to access important resources.

Authentication can consider:

* Username and password
* MFA
* User role
* Device identity
* Security status of the device

---

## 5.2 Least Privilege Access

Users should receive only the permissions required for their jobs.

For example:

| Department | Required Access                              |
| ---------- | -------------------------------------------- |
| HR         | HR applications and employee records         |
| Finance    | Financial applications and financial records |
| R&D        | Research systems and project data            |
| IT         | Administration systems                       |

Access should be reviewed regularly and unnecessary permissions should be removed.

---

## 5.3 Device Verification

The organization should not assume that every company laptop is secure.

Before allowing access, the device should be checked for things such as:

* Security software
* Operating system updates
* Encryption
* Device registration
* Security policy compliance

If a device does not meet the required security conditions, access can be restricted.

---

## 5.4 Network Segmentation

The enterprise network should be divided into separate security zones.

For example, HR, Finance, R&D and critical servers can be placed in separate network segments.

Access between these segments should only be allowed when it is required.

This helps prevent an attacker from moving easily from one department to another after compromising a device.

---

## 5.5 Continuous Monitoring

User and device activity should be monitored continuously.

Important events such as:

* Failed login attempts
* Unusual login locations
* Access to sensitive files
* Changes in permissions
* Suspicious network traffic

should be recorded and analyzed.

A SIEM system can be used to collect and analyze these logs.

---

# 6. Migration Plan

I would recommend migrating to Zero Trust in stages instead of changing the entire network at once.

## Phase 1: Identify Assets

The organization should first identify its:

* Users
* Devices
* Applications
* Servers
* Databases
* Important data
* Existing network connections

This provides a clear understanding of what needs to be protected.

## Phase 2: Strengthen Identity Security

MFA should be introduced for employees, especially for administrators and users accessing sensitive systems.

Existing accounts and permissions should also be reviewed.

## Phase 3: Secure Devices

Company devices should be registered and monitored.

Devices that are outdated, compromised or not compliant with security policies should not receive normal access.

## Phase 4: Implement Network Segmentation

The existing network should be divided into appropriate segments.

Sensitive systems such as Finance databases and important servers should receive additional access restrictions.

## Phase 5: Implement Least Privilege

Employee permissions should be reviewed department by department.

Users should only receive access that is necessary for their responsibilities.

## Phase 6: Continuous Monitoring

Finally, centralized logging and SIEM should be implemented.

Security teams can then monitor activity and respond to suspicious behavior.

---

# 7. Existing Network vs Zero Trust

| Security Area    | Existing Network      | Zero Trust Approach           |
| ---------------- | --------------------- | ----------------------------- |
| Authentication   | Mainly password based | MFA and identity verification |
| Internal trust   | Higher level of trust | No automatic trust            |
| Device security  | Limited checking      | Device compliance checking    |
| Permissions      | May be excessive      | Least privilege               |
| Network          | Less segmented        | Segmented                     |
| Remote access    | VPN focused           | Identity and policy based     |
| Monitoring       | Limited               | Continuous                    |
| Lateral movement | Easier                | Restricted                    |

---

# 8. Benefits of Migration

The proposed migration can provide several improvements.

### Improved Authentication

MFA reduces the possibility of an attacker gaining access using only a stolen password.

### Reduced Lateral Movement

Network segmentation and access policies make it more difficult for attackers to move between departments.

### Better Access Control

Least privilege ensures that users cannot access resources that they do not require.

### Better Protection for Remote Users

Remote access can be controlled based on the identity and security status of the user and device rather than simply allowing network access through a VPN.

### Better Visibility

Continuous monitoring allows suspicious activity to be detected earlier.

---

# 9. Challenges

The organization may face some difficulties while implementing Zero Trust.

### Cost

New security tools, identity systems and monitoring infrastructure may increase the initial cost.

### Employee Training

Employees need to understand MFA, security policies and changes to the way they access resources.

### Legacy Systems

Older applications may not support modern authentication or Zero Trust policies.

### Implementation Time

Migrating a large enterprise network cannot be completed immediately. It requires proper planning and testing.

### Management Complexity

There will be more policies and security controls to manage compared with a simple perimeter-based network.

---

# 10. Recommendation

Based on my analysis, I recommend that the enterprise move towards Zero Trust Architecture gradually.

The first priority should be securing user identities through MFA and proper access control. After that, device verification, network segmentation, least privilege and continuous monitoring can be introduced.

The existing firewall and VPN do not necessarily have to be removed. Instead, they should continue to be used as part of the overall security system while additional Zero Trust controls are introduced.

A phased migration would reduce the risk of disrupting normal business operations.

---

# 11. Conclusion

The analysis shows that a traditional enterprise network can have weaknesses when it relies mainly on perimeter security and assumes that internal users are trustworthy.

Zero Trust provides a better approach by removing this assumption and verifying users, devices and access requests before allowing access to resources.

The proposed migration focuses on MFA, device verification, least privilege, network segmentation and continuous monitoring.

I recommend implementing these controls gradually so that the enterprise can improve its security without completely replacing its existing infrastructure at once.

---

## References

1. NIST SP 800-207 – Zero Trust Architecture
2. Microsoft – Zero Trust Security
3. Cisco – Zero Trust Security
4. IBM – Zero Trust Security

---

**Prepared by:** [Your Name]
**Department:** Electronics and Communication Engineering
**Academic Year:** 2026
