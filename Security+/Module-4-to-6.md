# Module 4 - Identity & Access Management 

## Authentication 

As always, authentication needs to achieve the CIA triad. It needs to ensure that the credentials are secure(confidentiality), that the authentication cannot be bypassed(integrity) and that the mechanism used to authenticate does not cause undue delay or support issues(availability).

### Quick Password Security

Needs:

* To be long enough
* Complex with variety of characters
* Password expirations requiring change after set times
* Cannot reuse an old password. Needs to be distinct enough from old passwords.

There's also password managers & multi-factor authentication(MFA) which don't require much explanation. 

### Hard Authentication Tokens

Some sort of physical hardware device that generates an authentication token to verify the identity.

These can be smart cards(Like in a bank card), key fobs, USBs, security keys, or other standalone hardware device dedicated to authentication.

The token generated can be certificate-based([See module 3](Module-1-to-3.md)), OTP-based(One-Time Password, HOTP & TOTP are two standard algorithms to do so), or FIDO/U2F(Fast Identity Online & Universal 2nd Factor).

The latter FIDO/U2F is using a secondary U2F device after entering in a password to verify a public/private key "challenge" using that device as the authenticator. 

In the past, this would always require a password beforehand. However, FIDO2 removes that need for a password beforehand and can rely entirely on the key alone(Two standards: WebAuthn and CTAP(Client-to-Authenticator Protocol))


### Soft Authentication Tokens

These are software based authentication tokens. 

This would be like being sent a code via SMS, email, or phone calls. It could also be authenticated using a push notification on an app or using an authenticator app. 


## Access Management

Access control refers to how we manage and determine the permission levels to various resources. There are various models in how we do this. 

### Discretionary Access Control(DAC)

This model has the owner of that specific resource deciding who has access to it as well as what permissions they have.

Put simply, the owner has control. 

It's managed via things like Access Control Lists(ACLs), standard file share settings, etc.

### Mandatory Access Control(MAC)

This model has access controlled by a central authority determined by security clearance and labels.

For example, a document may have a security label as either:

* Top Secret
* Confidential
* Unclassified

In this case, only the group of people with the security clearance of Top Secret can access Top Secret documents.

You gain access by the security clearance that you are granted. 

### Role-Based Access Control(RBAC)

This is also centrally controlled. As it sounds, it works by giving users specific roles and having those roles assigned specific permission levels.

For example, we may have an administrator role, a manager role, or a staff role. Each of these three roles will have varying levels of permission levels.

These are security groups. I talked about it a bit previously [here](../TryHackMe/Cybersecurity-101/Module-1-to-3.md#security-groups) in the Active Directory module in TryHackMe as well.

### Attribute-Based Access Control(ABAC)

As this sounds, this sets access control based off the attributes and context of the user.

For example, let's say there is a payroll file that the only specific people with a specific combination of attributes should be able to access. These attributes could be like:

* Only finance employees
* Must be signed in via MFA
* Must use a compliant company device
* User must be part of a highly confidential security group

In this case, the access control wouldn't be a simple setting  to change but a set of conditions needing to be met before someone can access this payroll file. 


### Rule-Based Access Control:

As this also sounds, it is access control that's determined by if/then rules. 

For example, IF a user is attempting to access a file after 6:00pm, THEN block access to the file.

It applies globally and can be used in a variety of ways

**Principle of least privilege:** As always in security, this is the concept of a user having ONLY the sufficient permission levels needed for their work and nothing more. 

### User Account provisioning 

As part of user account provisioning, we need:
 
 * Identity proofing
 * Issuing of credentials
 * Asset allocation
 * Policy awareness and security education
 * Assignment of proper permissions and rights

Deprovisioning, in the case of someone leaving a company for example, would be the opposite. 

## Identity Management 
 




# Module 5 










# Module 6
