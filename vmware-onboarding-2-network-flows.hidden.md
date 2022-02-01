---

copyright:
  years: 2021, 2022
lastupdated: "2022-02-01"

subcollection: vmware-classic-journey

---

{{site.data.keyword.attribute-definition-list}}

# Plan Network Connectivity Flows
{: #vmware-onboarding-network-flows}

Taking the time to understand and plan network flows is a key ingredient to successful deployment. As you review this section, consider the connectivity requirements you have today but may also need in the future.
{: tip}

## Journey Map
{: #vmware-onboarding-network-flows-map}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/journey-map.png){: class="center"}

## Overview
{: #vmware-onboarding-network-flows-video-walkthrough}

By using NSX logical switches with your own IP addresses (BYOIP) you gain the greatest flexibility to manage and secure your workload network in the {{site.data.keyword.Bluemix_notm}}. However, with BYOIP comes the additional requirement of devising a strategy for connectivity from within your instance. There are four major areas of connectivity that need to be addressed:

1. VM to VM connectivity. How your VMs will be able to communicate with each other over the NSX software defined network. Considerations here include routing and whether microsegmentation will be implemented.
2. VM to public network (Internet) connectivity. Will your virtual machines connect to the Internet directly, utilize a gateway appliance such as FortiGate or vSRX, or utilize proxy servers deployed in the {{site.data.keyword.Bluemix_notm}} network or on your own network accessed via VPN or Direct Link.
3. VM to {{site.data.keyword.Bluemix_notm}} Private connectivity. Will your virtual machines require connectivity to services such as Cloud Object Storage or IBM Databases as a Service, and will that connectivity be secured through a gateway appliance or leverage the network address capabilities of NSX-T.
4. VM to on premise connectivity. Key to connectivity between your BYOIP NSX environment and on premise is the ability to perform route exchange between the two environments. Devising a solution to exchange routes using such technologies as BGP or GRE is essential to a complete working solution.


## Detailed Flows
{: #vmware-onboarding-network-flows-details}

In this section, detailed network flows will be reviewed. The following network architecture will be broken down into five different flows:

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow3.png){: class="center"}


### VM to VM traffic (overlay workload)
{: #vmware-onboarding-network-flows-vm-to-vm}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow2.png){: class="center"}


### VM to {{site.data.keyword.Bluemix_notm}} Private (10.x & 161.x) networks
{: #vmware-onboarding-network-flows-vm-to-ibmcloud}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow3.png){: class="center"}


### VM to Internet
{: #vmware-onboarding-network-flows-vm-to-internet}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow4.png){: class="center"}

### Internet to VM
{: #vmware-onboarding-network-flows-internet-to-vm}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow5.png){: class="center"}

### VM to Client Campus Network over VPN
{: #vmware-onboarding-network-flows-vm-to-client-vpn}

![Architecture](images/solution-vmware-onboarding-hidden/network-flows/flow6.png){: class="center"}

## Next Steps
{: #vvmware-onboarding-network-flows-next-steps}

The next step on the deployment journey is:

* [Prepare Your Cloud Account](/docs/vmware-classic-journey?topic=vmware-classic-journey-vmware-onboarding-prepare-account)

