# Enterprise Network Analysis - Moving Towards Zero Trust

## What I looked at

For this portfolio I considered a normal enterprise network with HR, Finance, R&D and IT departments. There are employee PCs, internal servers, firewall and VPN for employees working remotely.

The company already has a firewall so its not like there is no security at all. What I noticed is most of the security is based around getting into the network. Once someone logs in or connects through VPN, there can be more trust than there should be.

For example if an employee account gets compromised, the attacker might look like a normal user to the network. Same thing with an infected laptop which still belongs to an actual employee. So just being inside the network doesnt really mean its safe.

## Problems I found

The biggest one is unnecessary access. HR doesnt need R&D data and someone from R&D probably shouldnt just access finance systems. But in a badly configured network, getting into one part can make it easier to reach other systems.

Another problem is lateral movement. If one computer gets compromised, the attacker might try reaching more systems from there. If everything can communicate too freely, one compromised device can become a bigger problem.

Passwords are another problem. If someone steals a password through phishing and thats the only thing protecting an account, they could login as that person.

Also, having the correct username and password doesnt tell us if the laptop itself is secure. It could be outdated, missing updates or already infected.

## What I would change

I wouldnt remove the existing firewall or VPN because they still have a purpose. I would add more checks instead.

First thing I would do is MFA, mainly for admins and anyone accessing important systems. A stolen password alone shouldnt be enough.

Then I would check the permissions people already have. Sometimes users keep permissions from an old role or just have access they dont really need. I would remove unnecessary access instead of giving every employee broad permissions.

I would also separate the departments properly and restrict access between them. There can still be communication where its actually needed, but it shouldnt just be open by default.

For important systems, I would also consider the device being used. A company device that isnt updated or doesnt meet security requirements shouldnt get the same access as a secure device.

Monitoring is needed too because security doesnt just end after login. Failed logins, weird access attempts or a user suddenly trying to access something they normally dont use should be noticed.

## How I would move to Zero Trust

I dont think changing the whole network in one go would be practical.

I would first figure out what users, devices, servers and applications are actually in the network. Then I would start with user accounts because thats probably where an immediate improvement can be made. Enable MFA, remove unused accounts and check who has access to what.

After that I would work on separating the network and restricting unnecessary communication. I would do it carefully though because blocking things without understanding how company applications work could break legitimate services.

Then device checks can be added for sensitive resources and logging and monitoring can be improved.

The main idea isnt to block everyone from everything. That would just make the network unusable. Its more about checking if there is an actual reason for a particular user and device to access something.

## Why Zero Trust makes sense here

The traditional idea is kind of like trusting someone more once they're past the front door. Zero Trust changes that. Getting through the front door doesnt mean you automatically get access to every room.

The user should be verified, their permissions should make sense for what they are asking for and, where needed, the device should also meet security requirements.

Thats why the main changes I would recommend are MFA, least privilege, network segmentation, device checks and monitoring.

## Final thoughts

From looking at this network, I dont think the firewall is the main problem. The bigger issue is what happens after someone gets past the network boundary.

A compromised account is still dangerous even if the attacker logged in using valid credentials. A compromised device is still dangerous even if its physically inside the company.

So I would move towards Zero Trust gradually rather than replacing everything. Start with identities and permissions, then work on segmentation, device security and monitoring.

I think the biggest thing I understood from this is that Zero Trust isnt just one product or tool you install. Its more about changing how access is decided and why someone should get that access.

## References

NIST SP 800-207 - Zero Trust Architecture

Microsoft Zero Trust Security documentation

Cisco Zero Trust Security
