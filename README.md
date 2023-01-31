# Multi Tenant & Multi Cloud Or *How to move fast to Qlik Cloud for OEM?*

## Context

A Qlik Sense to Qlik Cloud migration can be performed with different strategies regarding your goals, your current cloud architecture and the expected values.
- Are you focusing on new customer deployment?
- Are you looking for On-Premise Qlik servers Footprint reduction?
- Do you want to leverage a specific Qlik Cloud added value product?
- ...

We recommend the [Qlik Migration Center](https://help.qlik.com/en-US/migration/Content/Migration/qliksense-qliksense-planning-your-migration.htm) to help you to define this strategy.

*Migration flow example from the migration center*
![image](https://user-images.githubusercontent.com/24877503/215733329-6efe4e09-062d-4a8e-99da-a3c14a3bf159.png)

Here a phased approach can minimize business disruption and enables cost control.

A distribution phase where dashboards are distributed from your client-managed platform to be consummed in Qlik Cloud allows you to :
- Move fast to the cloud (No data movement required).
- Leverage cloud capabilities on your existing application (Improve easily your product).
- Focus your efforts on the product front-end (Focus on end-users).

***This approach has been successful with many organizations. What would be the OEM multi-cloud architecture?***

## What is the target?

A Qlik Sense Enterprise multi-cloud deployment lets you deploy both Qlik Sense Enterprise on-premises and Qlik Sense Enterprise on cloud so users can develop apps on-premises and access them from the cloud.
For more information [Qlik Help](https://help.qlik.com/en-US/sense-admin/November2022/Subsystems/DeployAdministerQSE/Content/Sense_DeployAdminister/Multi-Cloud/Cloud-deployment.htm)

![image](https://user-images.githubusercontent.com/24877503/215739596-36406bef-6d7b-4d3a-aeb7-b2c2555f65ba.png)

In a [OEM multi-tenant](https://community.qlik.com/t5/Product-Innovation/Qlik-now-offers-Multitenant-Provisioning-in-Qlik-Cloud-for-our/ba-p/1993948) context, here's a architecture with multi-cloud deployment.

- The application are reloaded on a Qlik Sense Client Managed site.
- The applications are distributed at each reloads into the Qlik Cloud customer tenants.
- The customers consume the application on their own Qlik Cloud tenants. They can leverage QLik Cloud features on this application as alerting or automations. The client-managed RIM nodes (front-end engines) could be decommissioned.


![image](https://user-images.githubusercontent.com/24877503/215740998-97390b10-44cd-458c-9489-78d7b7bf2c8b.png)

***How to setup this OEM multi-cloud architecture?***

## How to setup?

*Assumption : we assume that customer tenants have been provisionned and configured.*

By making configurations in Qlik Sense Client-Managed and in your Qlik Cloud tenant, you can automate the distribution to cloud so that apps are automatically distributed to your Qlik Sense Enterprise SaaS deployment when you publish them to a stream.

Main steps are : 
1. Define a distribution rule : Similar to a Qlik Load balancing rule, it defines in wich conditions the app would be distributed and where.
2. Verify that your published app meet the rule requirements to be distributed
3. Define a "deployment", i.e. a Qlik Cloud customer tenant as a distribution target
4. Setup a specific IDP (Multi Cloud type) in the Qlik Cloud customer tenant
5. At the first distribution, the app must be published in a managed space. Then, it will be automatically replace at each reload.

*Multi Cloud configuration cheat sheet*
![image](https://user-images.githubusercontent.com/24877503/215744943-52d69714-e5be-461a-a345-d134318c9afc.png)

For more detailled information : [Qlik Help : Distributing apps from Qlik Sense Enterprise on Windows to Qlik Sense Enterprise SaaS](https://help.qlik.com/en-US/sense-admin/November2022/Subsystems/DeployAdministerQSE/Content/Sense_DeployAdminister/Multi-Cloud/distributing-apps-QSEoW-to-QCS.htm)

Note : In a multi-cloud distribution, based content and community content are distributed.

***Does it can be automated?***

### What 

## Attention points

## A first step in Qlik Cloud... What's the next move?

