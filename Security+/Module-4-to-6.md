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

## Access Management



## Identity Management 





# Module 5 










# Module 6
