# Planning for multi-region High Availability and Disaster Recovery with Azure Private Link 2

## Introduction

When working with Azure Private Link we are required to modify default DNS forwarding to make use of the Private Endpoints to access PaaS Services (And Azure Private Link Services) in a secure way. Specifically, by default, lookups to public FQDNs used by Microsoft PaaS Services (E.g. .database.windows.net for Azure SQL) will return a public IP address. We have to modify the configuration of DNS to return a Private IP address which maps to the NIC used by a Private Endpoint. 

**This article aims to explain how this requirement interacts with  designs that utilise multiple Azure Regions**, and therefore explores scenarios mapping to Disaster Recovery and High Availability requirements. We propose some possible topologies for DNS integration, and explain the interactions with some example PaaS services.

This article assumes familiarity with the concepts of Private Link, DNS and general use of Azure (VNets, resource, etc), please consider the following articles  pre-reading to build foundational knowledge before jumping in.

- aka.ms/whatisprivatelink - Introductory video on Private Link
- aka.ms/whyprivatelink - High level white paper exploring the requirement for Private Link
- aka.ms/privatelinkdns - Technical white paper introducing the DNS challenge when working with Private Link

## Basics - How PaaS DNS resolution works before and after Private Endpoints

I would really encourage you to at a minimum read this section of the above article by Daniel Mauser - https://github.com/dmauser/PrivateLink/tree/master/DNS-Integration-Scenarios#2-how-dns-resolution-works-before-and-after-private-endpoints - without this awareness the succeeding topics may be confusing.

In short, the 

## Important - Different PaaS offerings handle multi-region failover in different ways

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

## 

## Azure DNS Private Zones - a global resource

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

## Option 1 - consolidated global Azure DNS Private Zones

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

### Example - Azure Storage

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.


### Example - Azure SQL

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

## Option 2 - regional Azure DNS Private Zones

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

### Example - Azure Storage

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.


### Example - Azure SQL

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.

## Conclusion

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.