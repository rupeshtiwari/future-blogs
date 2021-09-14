---
layout: post
title: Cloud Security Best Practices
date: 2022-10-22 00:00 +0000
description: 'IMPORTANT: REMOVE LAYOUT: POST'
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/nU9cLAy.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - azure
  - tutorial
  - beginners
  - security
---

> Are you familiar with cloud layered security approach? Do you trust your on-premise users & systems more than outside then you are still exposed to vulnerabilities and cyber attack's. Let's learn what can we do to protect our applications, servers and networks over cloud?

Cloud Security best practices for applications, servers, and networks

You start securing your environment from network to server to application layers. Let’s discuss all of these best practices in detail in this article. For cloud protection I will refer to Azure cloud in this article. You can correlate [Azure Services & Infrastructures with AWS cloud](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/architecture/aws-professional/services&sa=D&source=editors&ust=1631655499424000&usg=AOvVaw0un7YO64VPN3Je-T-kjAAU) by referring to this article.

## Application Security

Why is application security important in your on-premise or cloud? Did you know 75% of organizations around the world have experienced some kind of phishing attack in 2021? Have you heard about a multi-layered approach to security? Cybercriminals know that web applications are the key to enter an organization's secret area and steal valuable information.

You can secure your web Applications in following manners:

- Single Sign-On
- Application Integrity
- Vulnerability Scanning and
- Virtual Patching

You have your on-premise or cloud line of business (LOB) applications and you want to secure it. Single Sign-On (SSO) is one of the crucial steps to securing your applications. You may ask what Single Sign-On will do in terms of security right? I used to think SSO is something where you once entered a password or once you logged in to your enterprise network then you don't need to login for other applications within your network applications. Then what exactly it is saving for security. Well it can save you from phishing attacks. Let's learn it by example. According to [Tessian Phishing Statistics 2020](https://www.google.com/url?q=https://www.tessian.com/blog/phishing-statistics-2020/&sa=D&source=editors&ust=1631655499425000&usg=AOvVaw22yXfgY7aPIPp8-zdz1YYA)  Last year 75% of organizations all over the world faced a phishing attack. Azure integrates your web applications with Azure active directory and provides single sign-on.

![](https://lh4.googleusercontent.com/WOTxkT8kOYqHTdnYd_01WfQe3YJmeJTcCOLPNSebc51hZH4cNQKTBL4xjalOncR-0Q8rHbI39TvtulRtkKHpJxQeR5vBIgT1Y70SnqLwTBA3fqHAfXWEnEvtvDn370xEn9MelTKu=s0)

Phishing attacks are the emails that will ask you to login to your application using your password. Examples of emails are: Please Read subject or Payment is Urgent Credential needed for login to secure etc. If you were using SSO and strong authentication in your organization which would eliminate the need for employees to ever manually enter passwords to access systems, applications or information. If an organization has SSO and an employee is asked for credentials, there is a strong likelihood it is a phishing attack.

Application Integrity

In 2020, the number of data breaches in the United [States came in at a total of 1001 cases.](https://www.google.com/url?q=https://www.statista.com/statistics/273550/data-breaches-recorded-in-the-united-states-by-number-of-breaches-and-records-exposed/&sa=D&source=editors&ust=1631655499426000&usg=AOvVaw0JUK1-xGiFvzPwoZzQ38Qx)

Therefore, as an organization you want to make sure your application data integrity is conserved. Application Integrity helps clients secure their organisations.There are many best practices as a policy and rules are available in Azure  policy that will enforce your application to adhere to them. Like using Https for web api, verify calling endpoint has valid certificate. Only clients that have a valid certificate will be able to reach the app. By default, incoming client certificates are disabled for Azure App Service web applications.

Azure has managed initiatives ( collection of policies ) for compliance domain and security control. Make sure you are applying one of them to your app service plan and other resources in workload.

Vulnerability Scans

[Edgescan’s 2021 Vulnerability Statistics Report](https://www.google.com/url?q=https://info.edgescan.com/vulnerability-stats-report-2021&sa=D&source=editors&ust=1631655499427000&usg=AOvVaw2EA08LZb2s4qyvyZLhke4A) analyzed the severity of web application vulnerabilities. It found that 50 percent of internal application vulnerabilities are considered high or critical risk. It also found that 32 percent of vulnerabilities in internet-facing applications are considered high or critical risk. According to [Verizon Data Breach Investigation Report](https://www.google.com/url?q=https://www.k2io.com/2021-verizon-data-breach-investigations-report-is-out&sa=D&source=editors&ust=1631655499427000&usg=AOvVaw3glCkblRnlfwhuYWs_k1NE) web applications remain the top vector used by hacking in breaches at over 90%.

![](https://lh5.googleusercontent.com/_WRFYBZwSXwDNHBHunS_UCzG2aXCbvdW4-YhWNBo74KZ6WdIpweLfqdb2VkzMtQytwhCOxav_eIMTIpiBgjCQm1qjClhmLIA31UDvcfPdu5HRoLr-Rv-IOvljLXgHT8-iRAFURLD=s0)

Therefore, you must scan your web app for vulnerability risk. Azure Web apps provide inbuilt tools for diagnoses and solving vulnerabilities problems.

![](https://lh5.googleusercontent.com/0Y50VLb-3YBL37lhVL9zFRJCEGc9HXv3wGT9SKL5bgqHkML1ostgippjF1g5_mKhqu4AB2sYIwIIGvKSrjtOATjHuiUT-PubJevidbwsoRXieMy4lsncIP0SRzZECnLyMnUnUl0o=s0)

App Service Diagnose and solve problems will also alert all the security risk associated with your web application.

![](https://lh5.googleusercontent.com/BtD4JuggPTczHGUzzLZOF-XNzbb1Wso6xhujOgG9Z37TZYHHfMzMId9N8rVSx2o8ZADoq3vQuvnsl4yQtG-q9yNDDas8f8KcSfRrn8vRZgjxfn8VjzLa6weYCbDk_2euy9hHRCEd=s0)

Virtual Patching

Virtual Patches are meant for protecting unitary vulnerabilities that are not already protected by the current [WAF Security Policy](https://www.google.com/url?q=https://success.qualys.com/discussions/s/article/000006325&sa=D&source=editors&ust=1631655499429000&usg=AOvVaw3y6hnv5URe1NB3zZvNuK6T).

Cyber criminals know web apps connect with back-end, active directory to get valuable business and intellectual data. [According to IBM data breach report 2021](https://www.google.com/url?q=https://www.ibm.com/security/data-breach&sa=D&source=editors&ust=1631655499429000&usg=AOvVaw0MyVRJT2QaAMjc1Kk2pH2s) data breach cost rose from USD 3.86 million to USD 4.24 million this is a 17-year history hike.

Nowadays due to the large volume of cloud migration and web application creation many organizations create too many web apps with too many vulnerabilities and they are left exposed to potential data breach via application. Many organizations even take their windows applications and convert them into web applications and without properly checking how to secure them. Additionally, many applications have written so poorly that they have security loopholes. So how to protect this issue?

If you are using Azure web apps which is PaaS (platform service) offered from Microsoft Azure then you are safe. Because AZure installs vulnerability scans and patches the OS frequently. In case you need to secure zero-day vulnerability on your web app then you can review your case with Azure and get that done for your dedicated host also.

Therefore, You should follow a well[ architected framework](https://www.google.com/url?q=https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by%3Ditem.additionalFields.sortDate%26wa-lens-whitepapers.sort-order%3Ddesc&sa=D&source=editors&ust=1631655499430000&usg=AOvVaw1QybVoko75jLUlPBm5hk4e) guideline for security for the web applications. Do code review and find out any security violation related code and remove them. Like sanitizing your incoming text from client to server to make sure you avoid running scripts injected by malicious users.

However, how would you protect from vulnerabilities in existing old applications? Suppose you have VM hosting web apps in the cloud then you own the patching of servers right? So if you left your VM with vulnerabilities then your VMs are the first choice for attackers.  The answer is that Virtual Patching is the technique where you work with WAS (web application scan) and WAF (Web application firewall). When you install virtual patch software then it will work with WAS to identify vulnerabilities and then automatically create rules in [WAF](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview&sa=D&source=editors&ust=1631655499431000&usg=AOvVaw2nixmVf80CP7SsCtlaiHpF). This way you endup protecting your app from existing vulnerabilities attacks without changing your source code.

## Network Security

Your environment Network can be secured by below practices

- Network segmentation
- Session Protection
- Monitoring
- Encryption

Network Segmentation

Network Segmentation can control your company network traffic flow. Your IT team can control who has access to which segment of the network. This improves security and performance  by dividing the entire network into segments. Example: In a financial bank you want to restrict all branch employees to not access financial reporting systems. With Network segmentation you can prevent the traffic to flow in the financial system segment and therefore, financial analysts can work better with excellent performance and also you secure your financial system from unauthorized systems. Also this way when your other branch got infected or attacked still financial systems will be safe. This is also a key technique for the [Zero Trust model](https://www.google.com/url?q=https://www.microsoft.com/security/blog/2019/10/23/perimeter-based-network-defense-transform-zero-trust-model/&sa=D&source=editors&ust=1631655499432000&usg=AOvVaw33sDfUR49V2xqOIytemJai).

Also you should learn [best practices of segmentation.](https://www.google.com/url?q=https://securityscorecard.com/blog/network-segmentation-best-practices-to-maximize-cybersecurity&sa=D&source=editors&ust=1631655499432000&usg=AOvVaw2jhxB9u41-yO5lkhC7U_32)

On-premises you can use a legacy way to create multiple DMZ (demilitarized zones) using internal firewalls and Access control Lists( ACLs) however that is more costly and time consuming. Nowadays you can apply tags on selected routes and group them virtually by tagging. Tag will enforce segmentation policy directly on the network equipment.

In Azure cloud you can achieve network segmentation as well by properly organizing network infrastructures. You have azure subscription, virtual network, network security group, application security group and azure firewall. These are great tools to create micro perimeters or segments.

When you use a virtual network (VNet)  then you get built-in segmentation. Because one VNet or VPC by default can not talk to others unless you set up peering between them. You can set up rules like for example, virtual network X can't talk with virtual network Y but can talk with virtual network Z, no Internet for Virtual network X except for access to \*.github.com, and so on.

In Azure cloud You can use subnets within a single virtual network and apply custom routes on each subnet to restrict the traffic flows. Or you can use an application gateway to each subnet. However this pattern where all workload is in one virtual network cannot span multiple regions since a virtual network is scoped to one region and can not span multiple regions. You can use multiple Virtual networks and use virtual network peering that way you get segmentation free and use NSG or ASG to enforce policies. However Virtual network peering is not transitive by nature.

![](https://lh4.googleusercontent.com/MPfyxW-A5K9pdTa8hMfCHOXdY1KYs5mHUKXbExJlgVYoS1rxNDI__upqIVdMf8GaPC_LIvpn9-8sFX46PD-O8KN543i-WzZpznhfPZHyr7MaNbj5lFCF65JlBK-ddEDOcGVcwVyH=s0)

To fix transitive issues I would recommend going to Hub and Spoke topology. Where you create one dedicated VNet as your hub network where all traffic passes through the hub virtual network and it can act as a gateway to other hubs in different regions. You can set up your security posture at the hubs so they get to segment and govern the traffic between the virtual networks in a scalable way. Whenever you want to add a new workload or new virtual network still security posture can be maintained without further big efforts. [Learn more about network segmentation in azure here.](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation&sa=D&source=editors&ust=1631655499434000&usg=AOvVaw1Fcc1sc2kcX9rRC_jOpYip)

Session Protection

You login to the system and establish a session with the server and do not close the browser to keep the session open. This will cause [session hijacking](https://www.google.com/url?q=https://www.globalsign.com/en/blog/session-hijacking-and-how-to-prevent-it&sa=D&source=editors&ust=1631655499435000&usg=AOvVaw3SLPaO-anFpnnw7kI1vAIJ) issues. Any cyber criminal can take advantage of your session and get valuable information out of it. According to the 2021[ Vulnerability Statistics Report](https://www.google.com/url?q=https://info.edgescan.com/hubfs/Edgescan2021StatsReport.pdf&sa=D&source=editors&ust=1631655499435000&usg=AOvVaw2ltkCuUW-bB_8HCGGSSLjZ) last year web applications got 37% of the XSS attacks. That could be prevented by Network session protection.

![](https://lh4.googleusercontent.com/W-kXNfYMCXvua-TFVFAItSrpxuknezP6j5j7ZKWfgIqlIPdhMROAeujuo56m3aXtNFPOuXDQwGMczBH4Pg1QMZbnhf6ZG1Avq7IH2fSpkXo_OXfFomjrLJ87_7EPjKdbsxgHVptR=s0)

There are below session hijack attacks:

- Cross-Site Scripting (XSS) : attackers exploit vulnerabilities within servers and inject scripts (JS, Active Directory, DOS) via web pages and retrieve information.

- Session Side Jacking: attackers can sniff through network packets and try to get the session key via session cookies and impersonate them to perform malicious actions. Mostly if you are accessing from public WIFI or unsecured hotspot this is possible.
- Session Fixation:  Attackers supply their session key and spoof the user into accessing a vulnerable server.

You can protect your network by using a web application firewall that will protect any session established to your network from the outside world. Also if you apply initiatives and policies to your resource groups then you will get enforced to implement certification based communication. That way you verify the outside  endpoints connecting to your server and save from session attacks.[ In the Azure web app you can apply SSL](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-bindings%23add-a-certificate-for-custom-domain&sa=D&source=editors&ust=1631655499437000&usg=AOvVaw0Bx_Jgf1rECttFkUuS6lDs) certificates also.

![](https://lh4.googleusercontent.com/nScpPGvBxvkJnbVk-w11gz23heQvy1Vqv2pA3oCO2W9k9G6gGNJdcgBYjnlYGPIZLa7HUJHHKh1RGbX3bxLey8RICN29MpMle0VMSjjBTJjwNoaiWOYO1SB0PGgLzbHaKNIAxlbn=s0)

Network Monitoring

Network security monitoring is good to detect and analyze activities potentially indicating security issues. Network cybersecurity monitoring can help protect your enterprise data—ranging from business stats to personal user information—from malicious actors and hackers. In your on-premises you can use the NMap tool to scan the network.

In [azure cloud Network Insights](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/azure-monitor/insights/network-insights-overview&sa=D&source=editors&ust=1631655499438000&usg=AOvVaw0uBarf9d94415-B9Kl7DC9) of Azure Security Center can give your comprehensive view of health and metrics for all deployed network resources. You can also see dependency flow, connectivity and traffic flow etc.

![](https://lh4.googleusercontent.com/yg7hY6f94QGe_9O5wJqFapu53hWAMHQQ1nNnYM8uMXmZJao_Q5RVXtiSisZUJWQ_cZb_aB_Ec4DWGmnQx7WMAGxOkPsVG0lDhjMAAtpKUFrIg6BeF6qJBqtnE0gBDXWZwMhx6doq=s0)

Encryption

Encrypting your data while it's in transit is an important step toward securing your applications. You can purchase certificates from a certificate authority and use them to encrypt the messages that pass in and out of your servers. This prevents unauthorized users from intercepting and examining the information in these messages while they're being transmitted.This also prevents [Man in the Middle Attack](https://www.google.com/url?q=https://en.wikipedia.org/wiki/Man-in-the-middle_attack&sa=D&source=editors&ust=1631655499438000&usg=AOvVaw0kXXDzHcRe5rnDGTHKkWA7).

You can use Application Gateway or front door in Azure or Web Application Firewall of AWS to protect your traffic and make sure they are encrypted. If you need end-to-end encryption, Application Gateway can decrypt the traffic on the gateway by using your private key and then re-encrypt again with the public key of the service running in the back-end pool.

Exposing your website or web application through the application gateway also means that you don't directly connect your servers to the web. You're exposing only port 80 or port 443 on the application gateway. Your web servers aren't directly accessible from the internet, reducing the attack surface of your infrastructure.

![](https://lh6.googleusercontent.com/cS_7g4qXD7BoPshcRPnfm8NMWBCSDXoJt1NXmAjWE14kXeaC7W37A3_3wjES9rJJVlKpIzjEBKrcoMMLq77ZOiI5GmcNrY0P7LB_GKPtoA46zKeWI6dRQhCmzN-eBugtpThlbwAu=s0)

Application Gateway can implement an SSL connection with clients. Application Gateway can also implement an SSL connection with the servers running your application.

## Server Security

Over the cloud you have to secure your virtual machines on your own. Cloud providers will take care of the cloud but you have to take care of whatever is in the cloud, especially virtual machines. When you provision virtual machines then you are responsible for patching and installing anti-virus etc on them.

Azure Security center can scan the network and based on security policy will also alert you for any pending patches on your VMs including cloud and on-premise any malware vulnerabilities found it will alert you. However, you have to take action and fix them.

You should consider

- Installing Anti Malware & Antivirus you can purchase them from Microsoft or Symantec etc.
- Secure your encryption keys created in VMs in the Azure Key Vault or AWS key management service (KMS) in aws cloud.
- Protect your server by frequently backing them up try [Azure Backup](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/backup/backup-overview&sa=D&source=editors&ust=1631655499440000&usg=AOvVaw05siGjV6Zs8SCOJjs8B6D3) this does not need any CaPeX to setup and gives you full protection of your application data.
- Protect from planned unplanned outages by implementing Site Recovery to keep your organization business continuity and disaster recovery so that your applications and servers are always running. [Azure Site Recovery](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/site-recovery/site-recovery-overview&sa=D&source=editors&ust=1631655499441000&usg=AOvVaw0so05atqdUjMhd16sFcIf5) helps to protect both on-premise and cloud workloads from disasters.
- Secure SQL data using Transparent Data Encryption (TDE) and column level encryption (CLE).
- Encrypt Virtual Machine disks to encrypt your VMs disks try[ Azure Disk Encryption ](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/security/fundamentals/azure-disk-encryption-vms-vmss&sa=D&source=editors&ust=1631655499441000&usg=AOvVaw0BbKVRADcWFg5UMkMg8Ocb)solution.
- Patch updates are installed in your machines.
- Secure VMs unauthorized access by implementing SSO and using identity-based access controls.

## References

[https://www.comparitech.com/blog/information-security/cybersecurity-vulnerability-statistics/](https://www.google.com/url?q=https://www.comparitech.com/blog/information-security/cybersecurity-vulnerability-statistics/&sa=D&source=editors&ust=1631655499442000&usg=AOvVaw3eFk4JclVqafXqx6c63aQX)

[https://blog.qualys.com/product-tech/2017/05/04/virtual-patching-a-lifesaver-for-web-app-security](https://www.google.com/url?q=https://blog.qualys.com/product-tech/2017/05/04/virtual-patching-a-lifesaver-for-web-app-security&sa=D&source=editors&ust=1631655499443000&usg=AOvVaw3fUvBCj6dmfxQbQYwURwYC)

[https://success.qualys.com/discussions/s/article/000006325](https://www.google.com/url?q=https://success.qualys.com/discussions/s/article/000006325&sa=D&source=editors&ust=1631655499443000&usg=AOvVaw2wMRdIm0zkuaaxvUj21kwt)

[https://www.microsoft.com/security/blog/2019/10/23/perimeter-based-network-defense-transform-zero-trust-model/](https://www.google.com/url?q=https://www.microsoft.com/security/blog/2019/10/23/perimeter-based-network-defense-transform-zero-trust-model/&sa=D&source=editors&ust=1631655499444000&usg=AOvVaw2CjKitwQmKAItT1tBd5LQc)

[https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/network-level-segmentation&sa=D&source=editors&ust=1631655499444000&usg=AOvVaw0vxe7VNkSEF58umNrDrkie)

[https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/web-application-firewall/afds/afds-overview&sa=D&source=editors&ust=1631655499444000&usg=AOvVaw1rYPBs0tTVwfx7YhNCk9vc)

[https://docs.microsoft.com/en-us/azure/azure-monitor/insights/network-insights-overview](https://www.google.com/url?q=https://docs.microsoft.com/en-us/azure/azure-monitor/insights/network-insights-overview&sa=D&source=editors&ust=1631655499445000&usg=AOvVaw0_m7eXegxJbwVttflnWMQ1)

[https://en.wikipedia.org/wiki/Man-in-the-middle_attack](https://www.google.com/url?q=https://en.wikipedia.org/wiki/Man-in-the-middle_attack&sa=D&source=editors&ust=1631655499445000&usg=AOvVaw08NnTHiAuJWvFik-i9Ra6i)

---

_Thanks for reading my article till end. I hope you learned something special today. If you enjoyed this article then please share to your friends and if you have suggestions or thoughts to share with me then please write in the comment box._

<div class="notice--success">
<strong>💖 Say 👋 to me!</strong>
<br>Rupesh Tiwari
<br>Founder of <a href="https://www.fullstackmaster.net">Fullstack Master </a>
<br>Email: <a href="mailto:rupesh.tiwari.info@gmail.com?subject=Hi">rupesh.tiwari.info@gmail.com</a>
<br>Website: <a href="https://www.rupeshtiwari.com">RupeshTiwari.com </a>
</div>
![](https://imgur.com/a32nUcu.png)
