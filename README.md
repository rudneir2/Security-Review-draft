# Security Review (draft) v0
Initial draft for the Microsoft Security review, with a focus on Azure, before it is added to the FT Wiki page.

## Table of Content

1. Introduction
2. Introduction to the Security Approaches
3. Why Security approaches matter to Security Review?
4. Let's put our hands-on
5. How to collect the right information to have a great Security Review recommendation
6. What diagrams and information are most important to start your security review?
7. How to document the IT customer environment
8.  Where to go to start providing Security recommendations (how to do it)
9.  Writing the recommendations
10. How to share the Recommendations with customer
11. Next steps after deliver recommendations to customer
12. FAQ

## 1. Introduction

Security Review in a Microsoft public cloud environment can involve not only Azure public cloud but also an on-premises environment and or another public cloud environment vendor, having a hybrid environment.

The picture below shows the big picture for a Security Review.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/6a931fbe-7a69-4fa1-86a0-7ac449aac223">

To proceed with a Security Review on customers that uses Azure public cloud environment, you need to understand some of the Security approaches considered by Microsoft.


## 2. Introduction to the Security Approaches

Below you will find what are those Security approaches, the most important reading about them, and the complete set of information for each of them.

### 2.1 Microsoft Security Benchamark

The Microsoft cloud security benchmark (MCSB) provides prescriptive best practices and recommendations using Microsoft Security services as its foundation. This is the main reason to consider this "approach" as one of the most important as reference for the Security Review.

https://learn.microsoft.com/en-us/security/benchmark/azure/overview


### 2.2 Cloud Adoption Framework (CAF) and Azure Landing Zone (ALZ)

Understand CAF, mainly the Azure Landing Zone, helps you (Security Engineer) to verify and guarantee that Azure environments in the customer you will do the Security Review, are configured according to the Azure Landing Zone best practices. This is a pre-requisite to initiate a Security Review.

https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/

### 2.3 Zero Trust

Understand Zero Trust is important mainly to use its pillars to make easier your Security Review work. Additionally Zero Trust helps you (Security Engineer) to cover important Security principle and make sure they will be covered during your review.

For **Zero Trust concepts**<br/>
https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-overview

For **Zero Trust pillars**<br/>
https://learn.microsoft.com/en-us/security/zero-trust/deploy/overview

### 2.4 Well Architected Framework (WAF)

Microsoft WAF presents cloud design patterns that support Security. It is a different approach compared to the other. It is not essential to Security Review, but it is good to understand and be aware about the security patterns presented by WAF.

https://learn.microsoft.com/en-us/azure/well-architected/security/design-patterns

### 2.5 Architecture diagram that shows how approaches helps to map customer environment and Microsoft security services

See the diagram below to understand how those approaches uses Microsoft security services as their foundation.

![image](https://github.com/user-attachments/assets/a400c425-4c0b-42cc-a8fb-bb3bb05404e5)

## 3. Why Security approaches matter to Security Review?

As of August 2024, there isn't a standardized method for conducting Security Reviews. Engineers and IT Architects may approach this task differently, but the objective remains the same: to ensure the Customer's IT environment is as secure as possible based on the findings and recommendations from the security review.

A good practice identified after multiple Security Reviews was to use Microsoft Security Benchmark as a reference for Microsoft Security Controls "and" Zero Trust pillars that helps in organizing customer IT environment in different groups, making easier to identify where we can provide security recommendations. 

That is what is going to be explained in the rest of this document.

## 4. Let's put our hands-on

Let's use an analogy. Imagine you're securing a new house, equipping it with fences, cameras, alarms, and other safeguards. To do this effectively, you need an in-depth understanding of the house—its layout, terrain, neighborhood, architectural plans, structure, and internal network.

The same principle applies to securing Azure. To provide robust security recommendations for Azure or a hybrid environment, you need a comprehensive understanding of your environment, just as you would need to know every detail of your house.

A deep knowledge of how Azure Networking functions, how Infrastructure services, Virtual Machines, and other endpoints interact with services like Storage, Databases, and Applications is critical for a thorough Security Review. Moreover, it's essential to understand how to authenticate and authorize all services, users, and applications in your environment. A clear grasp of your identity structure is crucial for delivering sound security recommendations.

By integrating all these aspects, you can ensure a successful and effective Security Review.


## 5. How to collect the right information to have a great Security Review recommendation

You can begin by sending an email to the customer, requesting any available architecture diagrams. The more you understand their environment, the better the security recommendations you can provide.

Once you have some diagrams, schedule a meeting with the customer to review them or gather additional information. In cases where the customer doesn't have any diagrams to share, use the initial meeting to collaborate with them on drafting some diagrams together.


## 6. What diagrams and information are most important to start your security review?

- Network topology diagrams.
- A list of endpoints (including VMs, desktops, and compute resources), detailing their placement within the network topology, operating system specifics, and the workloads they host.
- An identity structure diagram that includes identity providers, domain controllers, identity architectures, synchronization between cloud and on-premises identity providers, a list of privileged identity users, permissions, and more.
- Identify all users and types of users interacting with identity provider services (such as Entra ID or ADDS) within your identity architecture.
- Include any apps and databases that don’t run on VMs, such as Azure Web Apps, API Apps, Azure SQL Database, or other PaaS services, in your architecture design. It’s important to understand how these services communicate and their relationships within the environment.

## 7. How to document the IT customer environment

You should collect all the diagrams, Word documents, and spreadsheets provided by the customer and organize the information according to the Zero Trust Pillars. If possible, create a visual representation to better understand the relationships between the resources. However, if a visual format isn’t feasible, it’s perfectly acceptable to organize the information in documents or spreadsheets.

## 8. Where to go to start providing Security recommendations (how to do it)

Now that you have gathered all the information about the customer’s environment, the next step is to align it with the Microsoft security controls outlined in the Microsoft Security Benchmark. Before proceeding, ensure that you have organized the customer’s IT environment according to the Zero Trust pillars and have thoroughly reviewed the entire Microsoft Security Benchmark. This will help you fully understand the available security controls that can be applied to the customer’s environment.

### 8.1 To apply Security recommendations for Network:

- Review Microsoft Security Benchmark Network Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-network-security


### 8.2 To apply Security recommendations to Endpoints:

- Review Microsoft Security Benchmark Endpoint Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-endpoint-security


### 8.3 To apply Security recommendations to Infrastructure:

- Review Microsoft Security Benchmark Asset Management Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-asset-management

- Review Microsoft Security Benchmark Logging and Threat detection Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-logging-threat-detection

- Review Microsoft Security Benchmark Incident Response Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-incident-response

- Review Microsoft Security Benchmark Posture and vulnerability management Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-posture-vulnerability-management

- Review Microsoft Security Benchmark Backup and Recovery Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-backup-recovery

- Review Microsoft Security Benchmark Governance and Strategy Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-governance-strategy



### 8.4 To apply Security recommendations to Application:

- Review Microsoft Security Benchmark Devops Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-devops-security

- Review Microsoft Security Baseline for Azure App Services Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/app-service-security-baseline


### 8.5 To apply Security recommendations to Data (includes Storage services and Database services):

- Review Microsoft Security Benchmark Data Protection Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-data-protection

- Review Microsoft Security Baseline for Azure SQL database Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/baselines/azure-sql-security-baseline



### 8.6 To apply Security recommendations to Identity:

- Review Microsoft Security Benchmark Identity Management Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-identity-management

- Review Microsoft Security Benchmark Privileged Access Security Controls:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/mcsb-privileged-access


**NOTE:**
Within the Microsoft Security Benchmark, there are Microsoft Security Baselines that provide specific security controls tailored to Azure services and workloads. Depending on the resources in the customer's environment, you may need to consider different Microsoft Security Baseline controls to effectively support your Security Review.

See Microsoft Security Baseline details here:<br/>
https://learn.microsoft.com/en-us/security/benchmark/azure/security-baselines-overview

##  9. Writing the recommendations

Once you are familiar with all the Microsoft security controls, you can identify which controls are missing in the customer's environment. Your task will be to align the relevant Microsoft security controls with the customer's IT environment.

Next, you'll begin drafting recommendations, organized according to the Zero Trust pillars. Group your recommendations by categories such as Network Security, Infrastructure Security, Endpoint Security, Application Security, Data Security, and Identity Security.

These recommendations can be documented in a spreadsheet, Word document, or OneNote page—whichever format the customer prefers.


## 10. How to share the Recommendations with customer

You can send all the recommendations to the customer via email in your preferred format, as there is currently no standardized format for writing the recommendations. Ask the customer to review them, and once they have done so, you can schedule a meeting to go over the recommendations and address any questions they may have.

## 11. Next steps after deliver recommendations to customer

Allow the customer some time to review the recommendations. If possible, include one or two links with each recommendation that explain how to implement them.

- Kick-off meeting (understand the scope, present Microsoft Cloud security overview and Security approaches) **(1 hour)**
- Understand Customer environment **(1 to 3 hours)**
- Zero Trust approach and the ZT pillars **(1 hours)**
- Network security review **(1 to 2 hours)**
- Identity security review **(1 to 2 hours)**
- Infrastructure security review **(1 to 3 hours)**
- App and Data security review **(1 to 3 hours)**
- Writing and organizing the security recommendations (internal activity) **(2 to 4 hours)**
- Review recommendations with customer / Explain (overview) how to implement the recommendations **(1 to 3 hours)**

With the time estimated above, we may consider that a Security Review may take between 10 and 22 hours.

## 12. FAQ

### Do I need to be at Level 300 in every Security pillar (Network, Identity, Infrastructure, Endpoint, App, and Data) to deliver a Security Review?

While it would be ideal to have Level 300 expertise in each security pillar, it’s understandable that achieving this level of skill across all areas can be challenging. However, to effectively review and secure an environment, it’s crucial to understand how that environment functions as thoroughly as possible. Take networking, for example. The more you know about Azure VNET, UDR, VPN, Private Endpoint, DNS, Load Balancers, and other network components, the better you can implement security using tools like NSGs, ASGs, Firewalls, DDOS protection, Web Application Firewalls, and more.

If you're not yet at Level 300, you should aim to reach at least Level 200 in each area.

### Is Azure Landing Zone a prerequisite for a Security Review?

While it’s not explicitly stated as a requirement, beginning a Security Review without first ensuring that Azure Landing Zone best practices have been reviewed and implemented is like trying to add security to your home without first cleaning and organizing your house, backyard, landscaping, and infrastructure such as water, internet, and telephone.

If you're familiar with how Azure Landing Zone works, that's a significant advantage. You can review the key objectives of Azure Landing Zone with the customer in a single session. If you both decide to take a step back and implement Azure Landing Zone before starting the Security Review, it will greatly benefit the customer and enhance the overall effectiveness of the Security Review.

### Am I required to use MSB and Zero Trust to conduct a Security Review?

Answer: No, you are not obligated to use MSB and Zero Trust. However, having a solid reference for security controls is essential. In my experience, MSB and Zero Trust provide a strong combined framework. That said, you can also draw on other approaches, such as Azure Best Practices, the Cloud Adoption Framework, the Well-Architected Framework, or regulatory frameworks like NIST, CIS, and others.

### I’ve never conducted a Security Review before. How long will I take to be ready?

If you're already familiar with the pillars we’ve discussed and have a detailed understanding of a solid reference like MSB and its Security Controls, you should be ready to start a Security Review. It can also be helpful to shadow other engineers who have experience delivering Security Reviews to get a feel for the meeting dynamics.

If you have a good grasp of security, like SOC experience, but aren’t yet familiar with how all pieces of an IT environment work at a Level 200 or higher, you’ll need to study each area mentioned in this article. If possible, practice your new skills in a simulated environment. **Microsoft learn** offers all content you will need to be skilled on Network, Identity, Infrastructure services, Endpoint (Compute), Application, DevOps and Data services, including Storage services and Databases.










