---

copyright:
  years: 2021, 2022
lastupdated: "2022-02-01"

subcollection: vmware-classic-journey

---

{{site.data.keyword.attribute-definition-list}}

# Order vSRX Gateway
{: #vmware-onboarding-vsrx-gateway}

## Journey Map
{: #vmware-onboarding-vsrx-gateway-map}

![Architecture](images/solution-vmware-onboarding-hidden/order-vsrx/journey-map.png){: class="center"}

The information below will focus on one of our commonly used gateway devices, a vSRX. However, concepts can be applied to others as well.
{: tip}

The gateway device both provides a network boundary protecting all traffic entering and leaving the VCS environment as well as the ability to exchange the overlay network with your on-premise environment. 

![Architecture](images/solution-vmware-onboarding-hidden/order-vsrx/architecture-vsrx-callout.png){: class="center"}

## Detailed Steps
{: #vmware-onboarding-vsrx-gateway-prereqs}
{: step}

1. Go to the VMware Solutions Resources view and select the vCenter server instance.

   <img src="images/solution-vmware-onboarding-hidden/order-vsrx/vcs-server-list.png" alt="Architecture" style="zoom:67%;" />

1. Go to the Infrastructure tab and select the cluster.

   <img src="images/solution-vmware-onboarding-hidden/order-vsrx/vcs-infra-page.png" alt="Architecture" style="zoom:67%;" />

1. Scroll down and under network interface expand private VLAN. You will see a field named primary route which will have a value like bcr01a.wdc07 in the example below. This designates that the VCS cluster is in Washington DC 07, POD 1. <u>Take note of this information as it will be needed for the vSRX order</u>.

   <img src="images/solution-vmware-onboarding-hidden/order-vsrx/network-interface.png" alt="Architecture" style="zoom:67%;" />

1. From the hamburger menu choose Classic Infrastructure > Gateway Appliances (or go to https://{DomainName}/gen1/infrastructure/provision/gateway).
   <img src="images/solution-vmware-onboarding-hidden/order-vsrx/gateway-menu-item.png" alt="Architecture" style="zoom:50%;" />

   

1. Choose to order a new gateway device by clicking on **Order**. 

   1. Resource details:
      - Vendor: Juniper
      - Version: 20.4R2-S2 (which is the latest version at this time). While a 1Gpbs is available the VCS is 10Gbps.
      - License: Choose **standard. 
      - Hostname: <enter a hostname for example nf-gw01>
      - Domain name: <enter a domain for example wdc07.mycompany.local>
      - High Availability: We strongly recommend High availability remain checked
      - HA hostname: <enter a hostname for example nf-gw02>
      - HA domain: <enter a domain for example wdc07.mycompany.local>

   2. Location:

      - Location: Choose the data center your VCS is deployed in (In the example WDC07 is selected as that matches the VCS.)
      - Pod: Choose the pod your VCS is deployed in. (In this example, wdc07.pod01 is selected because "bcr01a – pod01" was derived from the previous step.)

   3. Server profile:
      - Server profile: The default selection (Intel Xeon 5218) may be used.
      - RAM: the default selection (32GB) may be used.
      - SSH keys: As vSRX’s are shared devices between multiple administrators we recommend that no key be added at this time and keys be added manually later.

   4. Storage disks: The default selection can be used.

   5. Network interface:
      - Interface: Public and private
      - Port redunancy: Automatic
      - Port speed: 10Gbps

   6. Add-ons:
      - All the remaining fields can be left at default.

   

1. Review the order and when satisfied click on **Create**.  Once complete, your device will have an `Active` status (as shown in the figure below).

   <img src="images/solution-vmware-onboarding-hidden/order-vsrx/vsrx-ordered.png" alt="vSRX Ordered" style="zoom:50%;" />


## Next Steps
{: #vmware-onboarding-vsrx-gateway-next-steps}

The next step on the deployment journey is:

* [Setup SSL VPN Client](/docs/vmware-classic-journey?topic=vmware-classic-journey-vmware-onboarding-ssl-vpn-client)

