# Phase 2 - Tickets

This phase is where I will be doing the actual simulated Help Desk work. 

I will be using a ServiceNow PDI(Personal Development Instance) as my ticketing system for creating and resolving tickets. 

I've already created an account with ServiceNow and received an instance. So now all that's needed before starting tickets is simply adding my users(Staff-1 & Staff-2) onto the PDI. 

I did so below:

<img width="1189" height="614" alt="Staff-1 User Creation" src="https://github.com/user-attachments/assets/4e3a6772-08f7-4655-8cd3-033b9cc231c1" />

<img width="1189" height="614" alt="Staff-2 User Creation" src="https://github.com/user-attachments/assets/798e543a-eee5-4119-8962-bb553c883a40" />

After this, we are now ready to start working on some tickets!


## Ticket 1 - Account locked out: Too many invalid attempts

This ticket will be a classic example of a user getting locked out of their account and needing our help to regain access. 

Set up: All we have to do is input an incorrect password 5 times into the `Staff-1` User account. Due to the Lockout GPO we set up in Phase 1, this will cause the user's account to be locked out.

The locked out screen looks like this:

<img width="1962" height="1294" alt="Staff-1 Locked out" src="https://github.com/user-attachments/assets/7bb2b880-4b32-47e7-88eb-025c31d3d462" />

All we have to do is head over to the AD US on the admin account, confirm the account is locked out, reset the password with a new temporary password(I just used "Password2" for simplicity), and prompt the user to change their password at the next login. The IT-Admin's POV looks like this:

<img width="1684" height="1244" alt="Password Reset" src="https://github.com/user-attachments/assets/d8ed42e1-2b1e-4d4d-8a8a-f8992425f225" />

Finally, the Staff User will go onto his account, use the temporary password, change his password to a new one, and can now work again!

<img width="1684" height="1244" alt="Change Password" src="https://github.com/user-attachments/assets/e4c2ac19-6f85-4fc4-acfc-b8595728c04f" />

The final ticket from ServiceNow looks like this.

<img width="1226" height="978" alt="Ticket #1" src="https://github.com/user-attachments/assets/cab9db2e-892f-4ce8-85c8-6714f683375e" />
