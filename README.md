# Planning for multi-region High Availability and Disaster Recovery with Azure Private Link

## Introduction

When working with Azure Private Link it is required to modify default DNS forwarding to make use of the Private Endpoints to access PaaS Services (And Azure Private Link Services) in a secure way. Specifically, by default, lookups to public FQDNs used by Microsoft PaaS Services (E.g. .database.windows.net for Azure SQL) will return a public IP address. We have to modify the configuraiton of DNS to return a Private IP address which maps to the NIC used by a Private Endpoint. 

This article is not a full explanation of the above, please consider the following articles required pre-reading to build foundational knowledge before implementing this solution.

- aka.ms/whatisprivatelink - Introductory video on Private Link
- aka.ms/whyprivatelink - High level white paper exploring the requirement for Private Link
- aka.ms/privatelinkdns - Technical white paper introducing the DNS challenge when working with Private Link

## Azure Firewall DNS Proxy

This feature was released in public preview on 30th June 2020. Please see the official documentation here. https://docs.microsoft.com/en-us/azure/firewall-manager/dns-settings

In short, when enabled, DNS Proxy will listen on port 53 for requests and forward them, by default to Azure DNS, or to the custom DNS server specified within Azure Firewall custom DNS settings.
