# Multi Tenant & Multi Cloud Or *How to move fast to Qlik Cloud for OEM?*

## Context

A Qlik Sense to Qlik Cloud migration can be performed with different strategies regarding your goals, your current cloud architecture and the expected values.
- Are you focusing on new customer deployment?
- Are you looking for On-Premise Qlik servers Footprint reduction?
- Do you want leverage a specific Qlik Cloud added value product?
- ...

We recommend the [Qlik Migration Center](https://help.qlik.com/en-US/migration/Content/Migration/qliksense-qliksense-planning-your-migration.htm) to help you to define this strategy.

*Migration flow example from the migration center*
![image](https://user-images.githubusercontent.com/24877503/215733329-6efe4e09-062d-4a8e-99da-a3c14a3bf159.png)

Here a phased approach can minimize business disruption and enables cost control.

A distribution phase where dashboards are distributed from your client-managed platform to be consummed in Qlik Cloud allows you to :
- Move fast to the cloud (No data movement required).
- Leverage cloud capabilities on your existing application (Improve easily your product).
- Focus your efforts on the product front-end (Focus on end-users).

*This approach has been successful with many organizations but how to do it in an OEM architecture with Multiple Tenants?*

## What is the target?

A Qlik Sense Enterprise multi-cloud deployment lets you deploy both Qlik Sense Enterprise on-premises and Qlik Sense Enterprise on cloud so users can develop apps on-premises and access them from the cloud.
For more information [Qlik Help](https://help.qlik.com/en-US/sense-admin/November2022/Subsystems/DeployAdministerQSE/Content/Sense_DeployAdminister/Multi-Cloud/Cloud-deployment.htm)

![image](https://user-images.githubusercontent.com/24877503/215739596-36406bef-6d7b-4d3a-aeb7-b2c2555f65ba.png)

In a [OEM multi-tenant](https://community.qlik.com/t5/Product-Innovation/Qlik-now-offers-Multitenant-Provisioning-in-Qlik-Cloud-for-our/ba-p/1993948) context, here's a architecture with multi-cloud deployment.

![image](https://user-images.githubusercontent.com/24877503/215740998-97390b10-44cd-458c-9489-78d7b7bf2c8b.png)

- The application are reloaded on a Qlik Sense Client Managed Site
- The applications are distributed at each reloads into the Qlik Cloud customer tenants
- The customers consume the application on their own Qlik Cloud tenants. They can leverage QLik Cloud features on this application as alerting or automations.

## How to setup?

### What 

## Attention points

## A first step in Qlik Cloud... What's the next move?

