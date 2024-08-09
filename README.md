# Security Review (draft) v0
initial draft for Microsoft Security review focused on Azure before being added to FT Wiki page

## Introduction

Security Review in a Microsoft public cloud environment can involve not only Azure public cloud but also an on-premises environment and or another public cloud environment vendor, having a hybrid environment.

The picture below shows the big picture for a Security Review.

![image](https://github.com/user-attachments/assets/e38cf7c2-23bd-45e3-a27a-0b15efe41377)

To proceed with a Security Review, sometimes referred to as Security Assessment or Security Deep Dive, you need to understand some of the Security approaches considered by Microsoft.


## Quick intro into the Security Approaches

Below you will find what are those Security approaches, the most important reading about them, and the complete set of information for each of them.

### Microsoft Security Benchamark

https://learn.microsoft.com/en-us/security/benchmark/azure/overview

**NOTE:** 
The Microsoft cloud security benchmark (MCSB) provides prescriptive best practices and recommendations using Microsoft Security services as its foundation. This is the main reason to consider this "approach" as one of the most important as reference for the Security Review.

### Cloud Adoption Framework (CAF) and Azure Landing Zone (ALZ)

https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/

**NOTE:** 
Understand CAF, mainly the Azure Landing Zone, helps you (Security Engineer) to verify and guarantee that Azure environments in the customer you will do the Security Review, are configured according to the Azure Landing Zone best practices. This is a pre-requisite to initiate a Security Review.

### Zero Trust

**Zero Trust concepts** - https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-overview

**Zero Trust pillars** - https://learn.microsoft.com/en-us/security/zero-trust/deploy/overview

**NOTE:** 
Understand Zero Trust is important mainly to use its pillars to make easier your Security Review work. Additionally Zero Trust helps you (Security Engineer) to cover important Security principle and make sure they will be covered during your review.

### Well Architected Framework (WAF)
https://learn.microsoft.com/en-us/azure/well-architected/security/design-patterns

**NOTE:** Microsoft WAF presents cloud design patterns that support Security. It is a different approach compared to the other. It is not essential to Security Review, but it is good to understand and be aware about the security patterns presented by WAF.

See the diagram below to understand how those approaches uses Microsoft security services as their foundation.

![image](https://github.com/user-attachments/assets/4f29d3c1-3615-44f5-8ebf-5197b899b28e)

## Why Security approaches matter to Security Review?

As of August 2024, there isn't a standardized method for conducting Security Reviews. Engineers and IT Architects may approach this task differently, but the objective remains the same: to ensure the Customer's IT environment is as secure as possible based on the findings and recommendations from the security review.

A good practice identified after multiple Security Reviews was to use Microsoft Security Benchmark as a reference for Microsoft Security Controls "and" Zero Trust pillars that helps in organizing customer IT environment in different groups, making easier to identify where we can provide security recommendations. 

That is what is going to be explained in the rest of this document.

## Let's put our hands on

Let's start with an analogy. Imagine you're building a new house and want to make it as secure as possible, using fences, cameras, alarms, etc. To achieve this, you need a deep understanding of your house—the layout, the terrain, the neighborhood, the architectural plans, the structure, and the network within it.

The same concept applies to Azure. To provide effective security recommendations in Azure or a hybrid environment, you need to have a comprehensive understanding of your environment, just as you would need to know every detail of your house.

Having a solid grasp of how Azure Networking operates, how Infrastructure services, Virtual Machines, and other endpoints interact with services like Storage, Databases, and Apps is crucial for a thorough Security Review. Additionally, understanding how to authenticate and authorize all services, users, and applications in your environment is essential. Your identity structure must be well-understood to provide sound security recommendations.

Combining all of these aspects will ensure a successful Security Review.


## How to collect the right information to have a great Security Review recommendation

You may start with an email by asking customer for all architecture diagram they have available. The most you know his environment the most great security recommendations you will be able to write.

Once you have some diagrams to start, you may set a meeting with customer to review those diagrams or ask for more information. There will be some times that customer doesn't have any diagrams to share. So, you will use the first meeting to start drafting some diagrams along with customer.![image](https://github.com/user-attachments/assets/34dd4afe-4c54-429d-a193-5573b3d6c60d)


## What diagrams and information is important so you may start your security review?

    - Network diagrams
   - List of endpoints (mostly VMs, Desktops and Compute resources), how they are set on the network topology, operating system details and workloads they run.
   - Identity structure diagram that shows identity providers, domain controllers, identity architectures, syncronization between cloud identity provider and on-premises identity provider, list of privileged identity users, permissions, etc.
   - Whoever (users and type of users) interact with identity provider services (such as Entra ID or ADDS) need to be clear in your identity architecture
   - If you have Apps and Database that doesn’t run on VMs, like Azure Web Apps, API Apps, Azure SQL Database and any other type of App and Database or Storage that runs on PaaS type of service, need to be listed or shows up in your architecture design. How they communicate with each other is important to understand all relationship among all the services![image](https://github.com/user-attachments/assets/64c9715d-1f37-49f6-9606-61c7f1120258)

## How to document the IT customer environment

You may collect all the diagrams or word documents or spreadsheets that customer provide you and organize those information into Zero Trust Pillars. If you can do it in a visual way, it is better to understand all resources relationships. If you can't have everything visually, it is fine to have the information in documents or spreadsheet.![image](https://github.com/user-attachments/assets/fd321ef3-a1f7-4f2d-bafc-7f4d35fdc4ff)

## Where to go to start providing Security recommendations (how to do it)

Now that you have all information regarding Customer environment, you will start matching customer IT environment with the Microsoft security control published on Microsoft Security Benchmark. Before you proceed, make sure you grouped customer IT environment according to Zero Trust pillars and you have read the entire Microsoft Security Benchmark controls, so you really understand all Security controls availble to be applied to Customer environment.![image](https://github.com/user-attachments/assets/84a09612-7fe5-41b1-a360-f1a30370f8bc)

### To apply Security recommendations for Network:

Review Microsoft Security Benchmark Network Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-network-security


### To apply Security recommendations to Endpoints:

Review Microsoft Security Benchmark Endpoint Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-endpoint-security


### To apply Security recommendations to Infrastructure:

Review Microsoft Security Benchmark Asset Management Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-asset-management

Review Microsoft Security Benchmark Logging and Threat detection Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-logging-threat-detection

Review Microsoft Security Benchmark Incident Response Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-incident-response

Review Microsoft Security Benchmark Posture and vulnerability management Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-posture-vulnerability-management

Review Microsoft Security Benchmark Backup and Recovery Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-backup-recovery

Review Microsoft Security Benchmark Governance and Strategy Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-governance-strategy



### To apply Security recommendations to Application:

Review Microsoft Security Benchmark Devops Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-devops-security

Review Microsoft Security Baseline for Azure App Services Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/app-service-security-baseline


### To apply Security recommendations to Data (includes Storage services and Database services):

Review Microsoft Security Benchmark Data Protection Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-data-protection

Review Microsoft Security Baseline for Azure SQL database Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-sql-security-baseline



### To apply Security recommendations to Identity:

Review Microsoft Security Benchmark Identity Management Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-identity-management

Review Microsoft Security Benchmark Privileged Access Security Controls:
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-privileged-access


**NOTE:**
As part of Microsoft Security Benchmark, there are Microsoft Security Baseline that brings security controls according to Azure services and workloads.
Depends on the Customer environment resources, you may consider different Microsoft Security Baseline controls to be used to support your Security Review.

See Microsoft Security Baseline details here:
https://learn.microsoft.com/en-us/security/benchmark/azure/security-baselines-overview

##  Writing the recommendations

Once you know all Microsoft security controls, you will be able to identify what security controls are missing in the customer environment. You will need to match the security controls offered by Microsoft that could be applied to customer IT environments.

This way, you will need to start writing the recommendations, again, based on Zero Trust pillars, grouping the recommendations according to Network security, Infrastructure security, Endpoint security, Application Security, Data security and Identity security.

The recommendations may be put in a spreadsheet or in word document or in an Onenote page. In the way customer prefer.


## How to share it with customer

You may send all the recommendations to Customer through email in the format you prefer (at this time there is not a standard to write the recommendations) and ask him to review all of the recommendations. After he review it, you may set a meeting to review and respond to questions on top of the recommendations.![image](https://github.com/user-attachments/assets/caf36b1f-9ab0-41ef-ad73-bb2164d8dfbd)

## Next steps after deliver recommendations to customer

Give a time to customer to review the recommendations. If you can, provide for every recommendation, one or two links that may explain how to implement such recommendations.

	- Kick-off meeting (understand the scope) (1 hour)
		○ Microsoft cloud Security overview
		○ Security approaches overview
	- Understand Customer environment (1 to 3 hours)
	- Zero Trust approach and the ZT pillars (1 hours)
	- Network security review (1 to 2 hours)
	- Identity security review (1 to 2 hours)
	- Infrastructure security review (1 to 3 hours)
	- App and Data security review (1 to 3 hours)
	- Writing and organizing the security recommendations (internal activity) (2 to 4 hours)
Review recommendations with customer / Explain (overview) how to implement the recommendations (1 to 3 hours)

## FAQ

### To deliver a Security Review should I have to be Level 300 on every Security pillar (Network, Identity, Infrastructure, Endpoint, App and Data) ?

If you have it, it will be great! It is hard to be skilled on everything, but to review an environment to implement Security, it is important you how that environment works as much as possible. Let's take network as an example. If you know how Azure VNET, UDR, VPN, Private Endpoint, DNS, Load Balancers, and other network components works, better you will implement security for it. By using accordingly, NSGs, ASGs, Firewall, DDOS, Web Application Firewall, and so on.

In case you are not Level 300, you should work to become at least Level 200.

### Azure Landing Zone is a pre-requisite for Security Review?

That is not stated in anywhere, however, start a Security Review without making sure that Azure Landing Zone best practices were already reviewed and applied, it is like to try to add security to your house, without to clean and organize all your house, backyard, landscaping, bedroom, and infrastructure such water, internet, telephone. : )

If you know how Azure Landing Zone works, that is great, because you can review in a single session the most important goals of Azure Landing Zone with customer, and if you both decide to give one step back to implement ALZ before start Security Review, that will be very beneficial to customer and for the result of the Security review.

### Am I obligated to use MSB and Zero Trust to deliver Security Review?

No. But you will need a good reference of Security controls. Per my experience, I found that good reference at MSB and Zero Trust combined.
But you can rely on different others approaches like Azure Best Practices, Cloud Adoption Framework, Well Architected Framework, or regulatory framework such as NIST, CIS, and many others.

### I have never delivered a Security Review, how long I will take to be prepared for it?

If you know how every pillars we are talking about works, if you know in details at least a good reference as MSB and all its Security Control, you will be good to start with Security Review. You may shadow other Engineers that already delivered Security Review to understand the dynamic of the meetings.

If you know Security but you don't know how an IT environment works in a level 200 at least, you just need to read it, and if you have time, apply those new skills in a simulated environment to practice. That below is a good list to start learning the most common services existent in most of IT environments.

Questions regarding this content: ruolivei@microsoft.com
![image](https://github.com/user-attachments/assets/6e6591fe-fb3d-473b-9cc5-6a68921f9016)

