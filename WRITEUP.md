## Comparison of Azure Virtual Machines vs Azure App Services

**1. Costs**

| Service               | Region         | Operating System | Type     | Tier     | Instance Series | Instance          | Hours | Monthly Cost |
|-----------------------|----------------|------------------|----------|----------|-----------------|-------------------|-------|--------------|
| Azure Virtual Machines| East US        | Windows          | OS Only  | Standard | D2 v3           | 2 vCPUs, 8 GB RAM | 730   | $137.24      |
| Azure Virtual Machines| Southeast Asia | Windows          | OS Only  | Standard | D2 v3           | 2 vCPUs, 8 GB RAM | 730   | $158.41      |
| Azure App Service     | East US        | Windows          | Web App  | Free     | N/A             | N/A               | N/A   | $0.00        |
| Azure App Service     | Southeast Asia | Windows          | Web App  | Free     | N/A             | N/A               | N/A   | $0.00        |

For VMs, the cost varies by region, with Southeast Asia being more expensive than East US for the same VM configuration. The monthly cost for a D2 v3 instance (2 vCPUs, 8 GB RAM) is $137.24 in East US and $158.41 in Southeast Asia. Meanwhile, for app service, there is no cost for the free tier, making it ideal for development and testing in both regions.

**2. Scaling:**

| Service               | Autoscaling                  | Load balancer       | Scale limit                                                                      |
|-----------------------|------------------------------|---------------------|----------------------------------------------------------------------------------|
| Azure Virtual Machines| Virtual machine scale sets   | Azure Load Balancer | Platform image: 1,000 nodes per scale set, Custom image: 600 nodes per scale set |
| Azure App Service     | Built-in service             | Integrated          | 30 instances, 100 with App Service Environment                                   |

App services has limited scalability and availability, it's suitable for small-scale applications like the CMS App as well as testing developments. Meanwhile Azure VMs offer more control, better scalability, and higher availability but come with higher costs and complexity. 

**3. Availability**
| Service               | Multiregion failover option                                                |
|-----------------------|-----------------------------------------------------------------------------|
| Azure Virtual Machines| Azure Traffic Manager, Azure Front Door, and cross-region Azure Load Balancer|
| Azure App Service     | Azure Traffic Manager and Azure Front Door                                  |

VMs offer a more comprehensive set of multiregion failover options, including the cross-region Azure Load Balancer, which can be beneficial for applications requiring high network performance and availability. On the other hand, for app service, with its support for Azure Traffic Manager and Azure Front Door, provides sufficient multiregion failover capabilities for most web applications, making it a simpler and more integrated solution for developers.

**4. Workflows**

For VMs, this nvolves more complex workflows, including setting up the environment, configuring the OS, and managing dependencies. It requires ongoing maintenance. In contrast, the app service free tier has a more simplified workflow with easy deployment and minimal maintenance. This is deal for quick development and testing, allowing developers to focus on the application itself.

## Justification for choosing App Service


When deciding between building the CMS App with the Azure Virtual Machine or the Azure App Service, I chose to deploy the application on the app service since it is the more suitable option with this use case. I chose this mainly because of cost efficiency, and specifically using the Free Tier. The app service's free tier offers easy deployment and minimal maintenance, which allowed me to focus on building the app. While it has limited scalability and availability, it's suitable for small-scale applications like the CMS App as well as testing developments. With app service, the workflow is simplified, as the platform handles much of the infrastructure management, reducing the need for manual setup and ongoing maintenance.

In contrast, Azure VMs, especially in the Basic, Standard, and Premium Tiers, offer more control, better scalability, and higher availability but come with higher costs and complexity. The workflow with Azure VMs involves more complex setup and maintenance, requiring us, developers, to manage the environment and dependencies. 

For production or larger-scale needs for CMS App like deploying it to a larger group of users, more countries, and making it highly available, upgrading to a paid tier of Azure App Service or using Azure VMs will be necessary.
