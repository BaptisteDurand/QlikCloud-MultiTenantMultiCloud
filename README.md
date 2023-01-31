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

![image](https://user-images.githubusercontent.com/24877503/215833942-ccc050d0-e007-4618-9f99-688fced48d3f.png)

In a [OEM multi-tenant](https://community.qlik.com/t5/Product-Innovation/Qlik-now-offers-Multitenant-Provisioning-in-Qlik-Cloud-for-our/ba-p/1993948) context, here's a architecture with multi-cloud deployment.

- The application are reloaded on a Qlik Sense Client Managed site.
- The applications are distributed at each reloads into the Qlik Cloud customer tenants.
- The customers consume the application on their own Qlik Cloud tenants. They can leverage Qlik Cloud features on this application as alerting or automations. The client-managed RIM nodes (front-end engines) could be decommissioned.

![image](https://user-images.githubusercontent.com/24877503/215833659-2783fd36-dbae-4bd7-a6b6-5a8e6472cae2.png)

***How to setup this OEM multi-cloud architecture?***

## How to setup

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

Note : In a multi-cloud distribution, base content and community content are distributed.

***Does it can be automated?***

## Automate it in your own process

*Pre requisites*

*We assume that customer tenants have been provisionned and configured.*

*Have a Qlik Sense client managed environment set up for multi cloud :*
- *Distribution rule (This step should be made once by environment)*
- *Customer App are published and setup following distribution rule (ex : custom properties). If needed, please refer to Qlik Sense Client Managed [QRS API](https://help.qlik.com/en-US/sense-developer/November2022/Subsystems/RepositoryServiceAPI/Content/Sense_RepositoryServiceAPI/RepositoryServiceAPI-Introduction.htm)*

Different API call to Qlik Sense Client Managed site and Qlik Cloud allow to setup a multi cloud distribution.
Main used API are :
- Qlik Cloud [Rest API](https://qlik.dev/apis#manage)
- Qlik Distribution API. This API are currently private so their use is unsupported at this stage.

1. Create a distribution depoyment to the customer tenant on Qlik Sense Client Managed.
2. Get the deployment token from this new deployment.
3. Get customer tenant access token with OAuth credentials
4. Create a Multi Cloud IDP
5. Force the distribution of the application
6. Execute the initial move of the application to a managed space

Here a [Postman collection](https://github.com/BaptisteDurand/QlikCloud-MultiTenantMultiCloud/blob/main/5.%20OEM%20Multitenancy%20-%20Multi%20Cloud%20Setup.postman_collection.json) showing this process.

![image](https://user-images.githubusercontent.com/24877503/215822429-9929a5dd-ef3c-4acc-aa0d-3414ad716911.png)

## Attention points

As mentionned previously some limitations or consideration must be remind for a large and automated deployment :
- Qlik Sense Client Managed Distribution API are currently private so their use is unsupported at this stage. Use at your own risk.
- A Qlik Sense Client Managed UI bug can appear to list all the deployments when you have above 50 deployments. 

## A first step in Qlik Cloud... What's the next move?

Multi-Cloud enable you to move fast your customer to Qlik cloud and leverage powerful Qlik Cloud unique capabilities.
RIM node (Qlik front-end servers) decommissionning allow you a fast ROI.

After this first step you can continue your Qlik Cloud journey in Data integration and movement to : 
- Access to your data directly from Qlik Cloud
- Reload your data in Qlik Cloud
- Perform Chanage Data Capture
- Deploy powerful AutoML algorithm.

Explore [integration.qlik.com](https://integration.qlik.com)
