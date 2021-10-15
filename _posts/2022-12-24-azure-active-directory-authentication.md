---
title: Azure Active Directory Authentication Basics
date: 2022-12-24 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: false
image: https://i.imgur.com/qxXxmBa.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - webdev
  - tutorial
  - beginners
  - cloud
---

> Azure Active Directory (AD) verifies the credentials that are username and password. It belongs to the Azure Identity Platform.

## What is Authentication?

Authentication (AuthN) is the process to prove that you are who you say you are. Microsoft identity platform uses [open Id connect protocol](https://openid.net/connect) for handling authentication.

## What is Authorization?

Authorization (AuthZ) is the act of granting an authenticated party permission to do something. Microsoft identity platform uses [OAuth2.0](https://oauth.net/2/) protocol for handling authorization.

## What are security Tokens?

Microsoft identity provider authenticates users and provides security toneks as [JWT](https://jwt.io/) that contains claims .

There are 3 types of [Security tokens:](https://docs.microsoft.com/en-us/azure/active-directory/develop/access-tokens)

1.  ID token
2.  Access tokens
3.  Refresh tokens

![](https://i.imgur.com/2BLbcE1.png)

**Id token**: is issued to the client during open id connect flow. ID token is used to authenticate users. It is provided by the authorized endpoint of the authorization server. It contains claims pertaining to the authentication of the end-user resource owner.

**Access token**: is issued by authorization server as a part of OAuth2.0 flow. It has information about the user & resource for which the token is issued. Access token enables clients to securely call protected web APIs and are used by web api to do authentication & authorization.

**Refresh token**: is issued by authorization server at the same time access token is issued. The access token expires in a short time. Client uses refresh token to get next access token.

## Validating Security Token

Authorization server signs the security token with a private key; it also publishes a public key. Web api verifies the signature of the token using public key. Client passess access token to the web api as bearer token in the authorization header.

![](https://i.imgur.com/PCRgN6Y.png)

## Security Principal 

Security Principal is a fancy name for various types of security tokens. Below are all called as security principal:

1.  User Principal
2.  Group Principal
3.  Service Principal
4.  Managed Identities

## What is Claim?

A claim provides assertions about one entity (client application) to another entity (Resource Server). Claim contains facts about the security principal that was authenticated by the authorization server. Claim provides info about below things:

1.  Security Token Server ( who generated )
2.  Date of token creation
3.  Subject
4.  Audience - Target application for which token generated

## What is an Application Model?

Azure AD has identity service and for identity provider to know which user has access to application you must register both user and application in the identity provider. This is the application model.

## Azure Active Directory Authentication

Azure Active Directory has below components for authentication:

1.  Self-Service Password Reset
2.  Azure AD Multi-Factor authentication
3.  Hybrid Integration to write password changes back to on-premises
4.  Hybrid integration to enforce password protection policy for an on-premise environment
5.  Passwordless authentication

## Azure AD Self-Service Password Reset

You can change or reset passwords without any admin help. Below are the self-services provided:

1.  Password changes
2.  Password reset
3.  Account unlock

All of the above activities can be done on cloud Azure AD & these are written back to the on-premises AD. So if you change password it will be synced to on-premises AD.

## Azure AD Multi-Factor Authentication

During authentication it will prompt additional information. 
![](https://i.imgur.com/L6gNomV.png)

Multi-factor authentication needs 2 or more information from below list:

1.  Something you know :- password
2.  Something you have :- Mobile or hardware key
3.  Something you are :- biometric (fingerprint, face scan )

![](https://i.imgur.com/1W7asfs.png)

## Password Protection by Azure AD

To enforce the use of strong passwords. Azure AD blocks weak passwords like (password123) etc. You can define a custom password policy for your organization. With hybrid integration you can even synchronize policies and weak/banned password list on-premise & enforce them.

![](https://i.imgur.com/oN6DpHN.png)

## Passwordless Authentication by Azure AD

You provide credentials using

1.  Biometric with windows hello for business
2.  FIDO2 security key

These authentication methods can not be easily duplicated by attackers therefore, they are highly safe.

---

_Thanks for reading my article till end. I hope you learned something special today. If you enjoyed this article then please share to your friends and if you have suggestions or thoughts to share with me then please write in the comment box._

<div class="notice--success">
<strong>💖 Say 👋 to me!</strong>
<br>Rupesh Tiwari
<br>Founder of <a href="https://www.fullstackmaster.net">Fullstack Master </a>
<br>Email: <a href="mailto:rupesh.tiwari.info@gmail.com?subject=Hi">rupesh.tiwari.info@gmail.com</a>
<br>Website: <a href="https://www.rupeshtiwari.com">RupeshTiwari.com </a>
</div>
![](https://imgur.com/a32nUcu.png){: .full}
