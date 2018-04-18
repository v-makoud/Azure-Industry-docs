---
# required metadata
title: Risk Grid Computing in Banking Overview 
author: dstarr
ms.author: dastarr
ms.date: 04/12/2018
ms.topic: article
ms.prod: non-product specific
description: Presents the business considerations of implementing Risk Grid Computing in Banking on Azure
---
# Risk Compute in Banking Overview

## Introduction

Financial risk analysts typically work in corporate finance and investment banking, analyzing the risk of their employer’s investment portfolios. Risk analysts review research, monitor economic and social conditions, stay abreast of regulations, and create computer models of the investment climate.

Most analysts spend quite a bit of time working with computer models to simulate and predict how financial conditions will change. When evaluating investment risks using computer models, the computational load of processing the predicative models (risk compute) can be quite large.

This article examines leveraging Azure services to augment current risk compute resources and optimize the cost and speed of risk compute workloads.

## Secure Connectivity to Azure

When building a risk compute solution on Azure, the business will continue to use existing applications such as trading systems, middle office risk management, risk analytics, and so on. Azure becomes an extension to those existing investments. When connecting to the cloud,the business needs to do so over a secure connection.

Before beginning any sort of integrated computing, Azure must be connected to the on-premise network. Azure offers two models for securely and reliably connecting current on-premise systems to Azure, [Microsoft Azure ExpressRoute](https://docs.microsoft.com/en-us/azure/expressroute/expressroute-introduction) and [VPN Gateway](https://docs.microsoft.com/en-us/azure/vpn-gateway/). Both offer secure and reliable connectivity, although there are differences in implementation, performance, cost and other attributes.

There are several physical network connectivity configurations beyond those in this logical model. To help with decisions and architectural guidance regarding connecting your network to Azure, see the article [Connect an on-premises network to Azure](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/) by the patterns & practices group.

## Batch Processing

Analysts need a simple and reliable way to provide their models to a [batch processing](https://docs.microsoft.com/en-us/azure/batch/) pipeline starting with data ingestion and flowing through data processing to analysis, where insights can be found in the resulting data.
Risk model input data comes in several forms, the most common being Excel files or .csv files. These files are often restructured into Parquet or RCFile formats, more suitable for processing the risk model in later stages of the risk computing pipeline. A common technique for parsing and processing these files is batch processing.

Batch processing allows many worker virtual machines to run in parallel as show in Figure 1. Processing data files and submitting results to machine learning systems or data stores are common tasks for the worker nodes. Given the jobs run by the worker nodes are created by the customer, almost any action may be taken in the batch job.

Figure 1

Azure provides an elegant solution for batch processing. Customers can choose to connect to data stored on premises after connecting Azure-based processing nodes to the on-premise networks. The customer can also upload data to an appropriate location within Azure, allowing for lower latency and higher bandwidth access to that data.