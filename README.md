#Qlik Cloud Site Inventory

##About
____________________________________________________________________________________
This App will provide information on your current tenant as follows:

	- Dashboard
	- Applications 
	- Prepare Data 
	- Data files 
	- Users 
	- Spaces 
	- Roles and Groups 
	- Data Sources 
	- Automations 
	- Predict 
	- Reloads Tasks 
	- Schedule Tasks 
	- Audit 
	- Setting 
	- Licenses

Installation

	- Download the QVF file.
	
	- Upload the app and publish the app in the same space where your monitor apps are. This app used the same data source that the Monitor apps. (monitoring_apps_REST)
	
	Optional

		In case this needs to be tested, you can copy the app in a personal o shared space and follow the next steps:
	
		- Create a REST Connection, and follow the next details 
		
			Example Connection: 
						URL: 			https://<tenant-name>.<region>.qlikcloud.com/api/v1/items
						Header: 		"Authorization"
						Header Value: 	"Bearer <token>"
			For reference on how to connect: 
						https://qlik.dev/tutorials/generate-your-first-api-key
			
		- Name the Connection in the Data load editor
			
			In the **Configuration** Section, replace the variable vRestPaginationConnector , below is an example
			
			Example: '<Space>:<Connection Name>'
       		Note: ':<Connection Name>' is the relative path which will check for a connection in the current space.
		
	
Reload Options
		
		The app can be reload as it is without any changes in the configuration, Also the app has several options, below are steps to setup and reload.
		
		- The app can be configure to load in three diferent modes
			
			- Complete 		In this mode is select by default and will load all data in the Application.
			- Configuration In this case only the configuration of the tenant will be loaded.
			- Test			Finally in this option, will only load user and space data, can be use to test this Application.
		
		- To select any of those options, the user must have reload priviedleges.
		
		- Open the Application and select the About sheet.
		
		- In the Load Mode Drop Down, select one of the three options and click, the Reload Button.
		
		If the appplication is Schedule to load, by default will be complete mode.

Install the Perfect pixel report

	1.- After the app is now loaded, open the reporting section.
	
	2.- Go the Template section and import the report file.
	
	3.- The Report can be Schedule or can be setup to be open on demand.


### TO DO
Usage examples Coming soon!
