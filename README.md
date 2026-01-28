# Qlik Cloud Site Inventory

## About

This App will provide information on your current tenant as follows:

* Dashboard
* Applications 
* Prepare Data 
* Data files 
* Users 
* Spaces 
* Roles and Groups 
* Data Sources 
* Automations 
* Predict 
* Reloads Tasks 
* Schedule Tasks 
* Audit 
* Setting 
* Licenses

## Installation

To install the Application please follow the next steps.

  - Download the QVF file.
  - Upload the app and publish the app in the same space where your monitor apps are, this app used the same data source that the Monitor apps. (monitoring_apps_REST)

Create a REST connection
  
   Example Connection: 
   
   	URL: 		  https://<tenant-name>.<region>.qlikcloud.com/api/v1/items
   	Header: 	  "Authorization"
   	Header Value: "Bearer <token>"
   
   For reference on how to create a api key go here: 
	         https://qlik.dev/tutorials/generate-your-first-api-key

	Edit the connection   
		- Check the Allow “WITH CONNECTION” 
		- In the Pagination Section 
			Pagination Type: NEXT URL 
			Next URL PATH: links/next/href 

   - Name the Connection in the Data load editor
        In the **Configuration** Section, replace the variable vRestPaginationConnector , below is an example
     
            Example: '<Space>:<Connection Name>'
            Note: ':<Connection Name>' is the relative path which will check for a connection in the current space.
	
## Reload Options
Schedule monthly data reloads for the application. This will enable you to monitor monthly usage trends.

There are several configuration settings that need to be modify before loading the app, this neecs to be change before publishing the app in a managed space.

    Example: '<Space>:<Connection Name>'
            Note: ':<Connection Name>' is the relative path which will check for a connection in the current space.
			vRestPaginationConnector is the name of the REST Connection, sintaxsis '<Space>:<Connection Name>' 

    vu_tenant_fqdn is the customer Tenant URL 
    	Example: let vu_tenant_fqdn = 'm8v7xge20rzvaph.us.qlikcloud.com'; 
	
	VloadMode this is the load mode, there are 3 modes ( 'Complete','Configuration','Test' )  Complete will load all items, in Configuration  
    only the tenant setting will be loaded, and finally there is a Test mode just validated that theda is being laoded 
    	Example: let VloadMode 	= 'Complete'; 
    			 let VloadMode 	= 'Configuration'; 
            	 let VloadMode 	= 'Test'; 
			 
	vInternal this value will hide or show sensitive data (emails, user name, app name's, etc) 1 is to Hide and 0 to show all valies. 
	    Example: let vInternal =  1; 
	
	VCustomerName This value is to have a value in the on-demand Report 
    Example: let VCustomerName	= 'Qlik International'; 
			
## Install the Perfect pixel report
- After the app is now loaded, open the reporting section.
- Go the Template section and import the report file. For more information please follow the next url https://help.qlik.com/en-US/cloud-services/Subsystems/Hub/Content/Sense_Hub/Reporting/cloud-in-app-reports-templates.htm
- The Report can be Schedule or can be setup to be open on demand. For more information follow the next url https://help.qlik.com/en-US/cloud-services/Subsystems/Hub/Content/Sense_Hub/Reporting/reports-on-demand-configure.htm
    

## TO DO
Usage examples Coming soon!
