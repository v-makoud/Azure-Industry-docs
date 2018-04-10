# Risk Compute in Banking Overview

## Introduction

Financial risk analysts typically work in corporate finance and investment banking, analyzing the risk of their employer’s investment portfolios. Risk analysts review research, monitor economic and social conditions, stay abreast of regulations, and create computer models of the investment climate. 

Most analysts spend quite a bit of time working with computer models to simulate and predict how financial conditions will change. When evaluating investment risks using computer models, the computational load of processing the predicative models (risk compute) can be quite large. 

This article examines leveraging Azure services to augment current risk compute resources and optimize the cost and speed of risk compute workloads.

## Secure Connectivity to Azure

When building a risk compute solution on Azure, the business will continue to use existing applications such as trading systems, middle office risk management, risk analytics, and so on. Azure becomes an extension to those existing investments. When connecting to the cloud,the business needs to do so over a secure connection. 

Before beginning any sort of integrated computing, Azure must be connected to the on-premise network. Azure offers two models for securely and reliably connecting current on-premise systems to Azure, [Microsoft Azure ExpressRoute](https://docs.microsoft.com/en-us/azure/expressroute/expressroute-introduction) and [VPN Gateway](https://docs.microsoft.com/en-us/azure/vpn-gateway/). Both offer secure and reliable connectivity, although there are differences in implementation, performance, cost and other attributes. 

![VPN or ExpressRoute](assets/overview-01.png "VPN or ExpressRoute")

There are several physical network connectivity configurations beyond those in this logical model. To help with decisions and architectural guidance regarding connecting your network to Azure, see the article [Connect an on-premises network to Azure](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/) by the patterns & practices group.


 