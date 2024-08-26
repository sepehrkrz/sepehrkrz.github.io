---
title: "Smart Contract for Crowdfunding: CampaignFactory and Campaign"
excerpt: "This project showcases a smart contract system for managing crowdfunding campaigns on the blockchain. It includes a factory contract for deploying new campaigns and a campaign contract with functionalities for contributions, funding requests, and approvals.<br> <br/><img src='/images/web3.jpeg'>"
collection: portfolio
---

## Overview

This project demonstrates the creation and management of crowdfunding campaigns using smart contracts on the blockchain. It involves two key contracts: **CampaignFactory** and **Campaign**. The **CampaignFactory** contract facilitates the deployment of new campaigns, while the **Campaign** contract manages the details of each crowdfunding campaign, including contributions, funding requests, and approvals.

[Link to GitHub Repository](https://github.com/sepehrkrz/web3)  
[View Live App on Netlify](https://grand-sorbet-9732b2.netlify.app/)

## Contract Structure

### CampaignFactory Contract

- **Purpose:** To create and deploy instances of the **Campaign** contract.
- **Functions:**
  - **createCampaign:** Creates a new **Campaign** contract with a specified minimum contribution and stores its address in the `deployedCampaigns` array.
  - **getDeployedCampaigns:** Returns the array of all deployed campaign addresses.

### Campaign Contract

- **Purpose:** To manage the operations of a single crowdfunding campaign.
- **Key Components:**
  - **Request Struct:** Stores information about each funding request, including:
    - Description of the request
    - Value (amount requested)
    - Recipient address
    - Completion status
    - Number of approvals received
  - **Manager:** The creator of the campaign who has special permissions.
  - **Minimum Contribution:** The minimum amount of Ether required to become an approver.
  - **Approvers Mapping:** Tracks contributors and their approval status.

## Key Functionalities

- **contribute:** Allows users to contribute Ether to the campaign. Only contributions above the minimum contribution are accepted.
- **createRequest:** Allows the manager to create a new funding request by providing a description, value, and recipient address. This function is restricted to the manager.
- **approveRequest:** Allows contributors to approve a specific funding request. Each contributor can approve a request only once.
- **finalizeRequest:** Enables the manager to finalize a request if it has received more than half of the approvals. Upon finalization, the funds are transferred to the recipient, and the request is marked as complete.
- **getSummary:** Provides an overview of the campaign, including the minimum contribution, contract balance, number of requests, number of approvers, and manager address.
- **getRequestCount:** Returns the total number of funding requests made in the campaign.

### Modifier: `restricted`

- This modifier ensures that certain functions, such as `createRequest` and `finalizeRequest`, can only be called by the campaign manager.

## Conclusion

This smart contract system provides a robust framework for managing decentralized crowdfunding campaigns. The **CampaignFactory** streamlines the deployment of new campaigns, while the **Campaign** contract offers comprehensive tools for campaign management, including contribution handling, funding requests, and approval processes. This project highlights the potential of blockchain technology in revolutionizing traditional crowdfunding mechanisms.

[Link to GitHub Repository](https://github.com/sepehrkrz/web3)  
[View Live App on Netlify](https://grand-sorbet-9732b2.netlify.app/)
