When deciding between building the CMS App with the Azure Virtual Machine or the Azure App Service, I chose to deploy the application on the app service since it is the more suitable option with this use case. I chose this mainly because of cost efficiency, and specifically using the Free Tier. The app service's free tier offers easy deployment and minimal maintenance, which allowed me to focus on building the app. While it has limited scalability and availability, it's suitable for small-scale applications like the CMS App as well as testing developments. With app service, the workflow is simplified, as the platform handles much of the infrastructure management, reducing the need for manual setup and ongoing maintenance.

In contrast, Azure VMs, especially in the Basic, Standard, and Premium Tiers, offer more control, better scalability, and higher availability but come with higher costs and complexity. The workflow with Azure VMs involves more complex setup and maintenance, requiring us, developers, to manage the environment and dependencies. 

For production or larger-scale needs for CMS App like deploying it to a larger group of users, more countries, and making it highly available, upgrading to a paid tier of Azure App Service or using Azure VMs will be necessary.


