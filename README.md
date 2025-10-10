First, one must understand the inner workings of Kerberos before diving into the abuse primitives. Kerberos works on a system of tickets, where principals, users and computers, are authenticated by a central, trusted server (The Key Distribution Center, and its sub components. The server permits the principals to access services without having to provide their password with each use. Kerberos relies on shared-secret cryptography to establish a trust relation with clients, because it assumes that there is no transport encryption on the networks. It also assumes that packets can be read/modified/replayed.

The Key Distribution Center (KDC) And Its Subcomponents: 
A database which consists of all of the principals and their associated secret keys(used to authenticate the user), flags and permissions regarding the account, policy attributes, and more.
The Authentication Server (AS). 
A Ticket Granting Server (TGS).

What is a service? 
A service is a resource that can be accessed by a principal.  Each service is identified by an SPN (Service Principal Name)!! A service can be anything from a ssh login that is validated by kerberos, directory services like LDAP, file sharing like NFS, and more.

The Ticket Granting Ticket (TGT):
	-A Ticket Granting Ticket (TGT) is granted to a principal after the AS validates their identity via the KDC (Key Distribution Center).

How does a principal access a service using Kerberos authentication? 
	-First a request needs to be made from the TGS (Ticket Granting Server), then the Ticket Granting Ticket (TGT) is sent to the KDC.

What information inside of the PAC or Privileged Attribute Certificate?
The PAC includes information about the principal, such as their RID, domain group membership, user SID, group SIDS, a checksum which verifies that the PAC hasn’t been tampered with, and more. It basically contains the information pertaining to what the principal can do. 
