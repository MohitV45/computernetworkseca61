Enterprise Network Analysis. Moving Towards Zero Trust

What I looked at

For this portfolio I considered a company network with different departments like HR, Finance, R&D and IT. There are computers for employees servers inside the company a firewall and a VPN for employees who work from home.

The company already has a firewall so it is not like there is no security. What I noticed is that most of the security is about getting into the network. Once someone logs in or connects through VPN the network trusts them much.

For example if an employee account gets hacked the hacker might look like an user to the network. The same thing happens with a laptop that still belongs to an actual employee. So just being inside the network does not really mean it is safe.

Problems I found

The biggest problem is that employees have much access. HR does not need to see R&D data and someone from R&D probably should not just access finance systems.. In a badly configured network getting into one part can make it easier to reach other systems.

Another problem is that hackers can move easily from one computer to another. If one computer gets hacked the hacker might try to reach systems from there. If all computers can communicate freely one hacked device can become a bigger problem.

Passwords are another problem. If someone steals a password through phishing and that is the thing protecting an account they could login as that person.

Also having the username and password does not tell us if the laptop itself is secure. It could be outdated, missing updates or already infected.

What I would change

I would not remove the existing firewall or VPN because they still have a purpose. I would add checks instead.

First I would add Multi Factor Authentication, for admins and anyone accessing important systems. A stolen password alone should not be enough.

Then I would check the permissions people already have. Sometimes users keep permissions from a role or just have access they do not really need. I would remove access instead of giving every employee broad permissions.

I would also separate the departments properly. Restrict access between them. There can still be communication where it is actually needed. It should not just be open by default.

For systems I would also consider the device being used. A company device that is not updated or does not meet security requirements should not get the access as a secure device.

Monitoring is needed too because security does not just end after login. Failed logins, weird access attempts or a user suddenly trying to access something they normally do not use should be noticed.

How I would move to Zero Trust

I do not think changing the network in one go would be practical.

I would first figure out what users, devices, servers and applications are actually in the network. Then I would start with user accounts because that is probably where an immediate improvement can be made. Enable Multi Factor Authentication remove accounts and check who has access to what.

After that I would work on separating the network and restricting communication. I would do it carefully though because blocking things without understanding how company applications work could break services.

Then device checks can be added for resources and logging and monitoring can be improved.

The main idea is not to block everyone from everything. That would just make the network unusable. It is more about checking if there is a reason for a particular user and device to access something.

Why Zero Trust makes sense here

The traditional idea is of like trusting someone more once they are past the front door. Zero Trust changes that. Getting through the door does not mean you automatically get access to every room.

The user should be verified their permissions should make sense for what they're asking for and where needed the device should also meet security requirements.

That is why the main changes I would recommend are Multi Factor Authentication, privilege, network segmentation, device checks and monitoring.

Final thoughts

From looking at this network I do not think the firewall is the problem. The bigger issue is what happens after someone gets past the network boundary.

A compromised account is still dangerous even if the attacker logged in using credentials. A compromised device is still dangerous even if it is inside the company.

So I would move towards Zero Trust gradually than replacing everything. Start with identities and permissions then work on segmentation, device security and monitoring.

I think the biggest thing I understood from this is that Zero Trust is not one product or tool you install. It is more, about changing how access is decided and why someone should get that access.

References

NIST SP 800-207. Zero Trust Architecture

Microsoft Zero Trust Security documentation

Cisco Zero Trust Security
