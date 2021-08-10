---
title: Azure VPN Gateway for Site to Site Connection
date: 2022-08-06 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/qxXxmBa.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - webdev
  - tutorial
  - beginners
  - azure
---

> A virtual private network (VPN) is a type of private interconnected network. VPNs use an encrypted tunnel within another network.

## Azure VPN gateways

A VPN gateway is a type of Virtual Network Gateway.

![](https://i.imgur.com/miGEdkX.png){: .full}

If you want to setup below connections then you need VPN Gateway:

- Connect on-premises data centers to Azure virtual networks through a _site-to-site_ connection.
- Connect individual devices to Azure virtual networks through a _point-to-site_ connection.
- Connect Azure virtual networks to other Azure virtual networks through a _network-to-network_ connection.

![](https://i.imgur.com/5ChrRwG.png){: .full}

{: .notice--success}
🏆 **Pro Tip** \
\
You can deploy only one VPN gateway in each virtual network, but you can use one gateway to connect to multiple locations.

## VPN Types

The main difference of these two types of `VPNs` is how traffic to be encrypted is specified.

![](https://i.imgur.com/Fo4sVr3.png){: .full}

- policy-based
- route-based

## Policy-based VPNs

Policy-based VPN gateways specify statically the IP address of packets that should be encrypted through each tunnel.
![](https://i.imgur.com/YbGDtnR.png){: .full}

- Support for `IKEv1` only.
- Used for compatibility with legacy on-premises VPN devices.
- The source and destination of the tunneled networks are declared in the policy and don't need to be declared in routing tables.
