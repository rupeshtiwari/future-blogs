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

> A virtual private network (VPN) is a type of private interconnected network. VPNs use an encrypted tunnel within another network. I will explain what is VPN Gateway and how to deploy in Azure.

## Azure VPN gateways

A VPN gateway is a type of Virtual Network Gateway. `ExpressRoute` is another gateway type which is most efficient and costly. I will focus more on VPN gateway.

![](https://i.imgur.com/LXoNdle.png){: .full}

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

![](https://i.imgur.com/9gsqcHn.png){: .full}

- policy-based
- route-based

## Policy-based `VPNs`

Policy-based VPN gateways specify statically the IP address of packets that should be encrypted through each tunnel.
![](https://i.imgur.com/veC2bks.png){: .full}

- Support for `IKEv1` only.
- Used for compatibility with legacy on-premises VPN devices.
- The source and destination of the tunneled networks are declared in the policy and don't need to be declared in routing tables.

## Rout Based VPN

With route-based gateways, `IPSec` tunnels are modeled as a network interface or VTI (virtual tunnel interface). IP routing (static routes or dynamic routing protocols) decide across which one of these tunnel interfaces to send each packet.

Both types of VPN gateways (route-based and policy-based) in Azure use pre-shared key as the only method of authentication. Both types also rely on Internet Key Exchange (IKE) in either version 1 or version 2 and Internet Protocol Security (`IPSec`). IKE is used to set up a security association (an agreement of the encryption) between two endpoints. This association is then passed to the `IPSec` suite, which encrypts and decrypts data packets encapsulated in the VPN tunnel.

## Components of VPN Gateway in Azure

You need below 6 resources to be created and configured in order to setup site-to-site connection with VPN Gateway:
![](https://i.imgur.com/40PIjPB.png){: .full}

- **VNet**: Only one VPN Gateway can be deployed in a Single VNet. While creating VNet give enough address space to accommodate future subnets.
- **GatewaySubnet**: You need a dedicated subnet for VPN Gateway. You have to call this as `GatewaySubnet`. You can not use this subnet for other service. Make sure you give `/27` address mask to make sure you have enough IP addresses for future growth. Also remember sometime you want to put 2 VPN Gateways in `Active/Standby` or `Active/Active` mode within this subnet in order for redundancy.
- **Virtual Network Gateway**: Create Virtual Network Gateway of `VPN` type. This will route the traffic from on-premise to Azure VNet and vice-versa.
- **Public IP address**: Create `Dynamic Public IP Address` resource. This address will only change if you delete and recreate the VPN. This IP will be internet facing and your on-premise VPN Device can point to this IP Address.
- **Local Network Gateway**: This is created to represent on-premise network's configurations. This configuration includes the on-premises VPN device's public `IPv4` address and the on-premises routable networks. This information is used by the VPN gateway to route packets that are destined for on-premises networks through the `IPSec` tunnel.
- **Connection**: Create a `connection` resource. Connect VPN Gateway with on-premise VPN Device IPv4 address. Connect VPN Gateway with it's Public IP Address.

![](https://i.imgur.com/mV537mU.png){: .full}

## On-Premise resources

You need Physical VPN Device and a Public-Facing IPv4 address in your data center to connect to Azure resources.

## High Availability

Since all traffic has to go from VPN Gateway. You must think of what will happen in case of any issues. We have to work on fault tolerance.

You can use 2 VPN Gateways one in `Active/Standby` and other is in `Active/Active` mode.

### Active / Standby

On any planned maintenance or un-planned interruption affects active instance then within `90` seconds the standby gateway will become active `automatically` without any human involvement. This is excellent feature.

![](https://i.imgur.com/fYtUs8W.png){: .full}

### Active/ Active

In this mode you have to deploy `2 VPN gateways` with 2 `distinct IP Addresses`. Then on-premise will have `2 VPN devices` to connect with them. With this you see how much traffic can be distributed among these 2 gateways.

![](https://i.imgur.com/Uc42Bje.png){: .full}
