---
title: "Authentication with CloudMC"
slug: authentication
---


### Authentication and security in CloudMC

CloudMC provides three ways to manage user accounts, providing extensible support for various login mechanisms.

   - **Internal:**  The default mechanism for managing user accounts.  Credentials are stored in CloudMC's internal database.
   - **LDAP:**  CloudMC supports authentication through an LDAP server, including Microsoft Active Directory.
   - **OpenID Connect:**  Provides authentication for CloudMC user accounts through external identity providers.

Internal and LDAP authentication are enabled at the organization level, by a user account with the *Administrator* role or any other role with the *Organizations: Manage* permission.

Support for [OpenID Connect](https://en.wikipedia.org/wiki/OpenID_Connect) enables CloudMC to authenticate users with external identity providers using the OAuth 2.0 protocol.  OpenID Connect is a system-wide feature and is enabled by a user account with the *Reseller* role or any role with the *Authentication: Manage* permission.

## Acting as an identity provider

### Configuring internal authentication

Link to LDAP article
Link to OIDC article
Link to identity provider article
