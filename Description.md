# Creating a WebProject In NetBeans

## Table of Contents
*Description
*Features of JsonPowerDB
*Benefits of using JsonPowerDB
*Examples of use
*Project status
*Sources


## Descripion:

    
      Javascript Object Notation is having explosive growth in recent years due to it's speed.If a query runs 10 times faster on a database it should increase the speed theoretically by 10 times and practically by 7-8 times,so market will always welcome this new technology as it increases efficency and reduces cost.
   

## Features of JsonPowerDB:
   
      1.It is multi-mode DataBase.
	  2.It is simple to use.
	  3.Schema free
	  4.Multiple security layers.
	  5.A single instance-Million Indexes.
	 
## Benefits of using JsonPowerDB:

      1.Minimum Development Cost.
	  2.Maximum Dta processing Performance
	  3.Pluggable wth new algorithms.
	  4.Fils Gap from data to database.
	  5.Compatible with any software application which needs backend database.
	  6.Live working with HTML templates.
	 
## Examples Of use:
   To use JPDB we must create acn account in login2explore initially.
   Steps to create an account,
   Steps for creating developer account:

		*Visit: http://jsonpowerdb.com:5577/user/index.html
		*REGISTER
		*After registration check your email-id for password.
		*Login at http://jsonpowerdb.com:5577/user/index.html using your email and password received.
		*First of all change password - Left Navigation >> Change Password.
		*Login with new password. 
		*Add Talend API Tester  to your chrome
  Generate your connection token by going into tools at	http://jsonpowerdb.com:5577/user/index.html
  Now open Talend API Tester And save a file and add following commands to the body to create a database.
  
  ### PUT COMMAND:
  
   {
    "token": "90937141|-31948799583822676|90931330",
    "cmd": "PUT",
    "dbName": "SAMPLE",
    "rel": "Emp-Rel",
  	"type":"PUT",
    "jsonStr": {
        "empId":"1",
        "empName": "Sulbha Mishra",
        "empEmail": "sulbhamishra@gmail.com",
    	}
	}
	
	The above code will create a database Employee with relation Emp-Rel with name,id,email as coloumns.
	
	
	
  ### GET COMMAND:
  
	
	{
    "token": "90937141|-31948799583822676|90931330",
    "cmd": "GET",
    "dbName": "Employee",
    "rel": "Emp-rel",
    "jsonStr":{
        "name": "Sulbha Mishra"
    }
	}
	
	The above code will retrieve given database record with relation Emp-Rel which has the given name.
	
	
	
  ### UPDTAE COMMAND:
  
  
	
	{
    "token": "90937141|-31948799583822676|90931330"
    "cmd": "UPDATE",
    "dbName": "Employee-DB",
    "rel": "Employee",
    "jsonStr": {
       "1":{
        "name": "Gargee Mishra",
      	}
       
  	 	}
	}
	
	The above code will update given database record with relation Emp-Rel which has the given name.
	
	
  ### DELETE COMMAND:
  
  
	
	{
    "token": "90937141|-31948799583822676|90931330",
    "cmd": "REMOVE",
    "dbName": "Employee",
    "rel": "Emp-Rel",
 		"record" : 1
       
    }
	
	The above code will delete given database record with relation Emp-Rel.
	
	
	
  
  ### Note : please use the token generated before in above code and the base url to upload the database.



## Project status:
   Created a Dynamic webpage where in user can enter enter his name,Id and email and all those dta get stored in the database created 
   Please refer Readme.md for the code
   Data base used for the project:
   
   {
    "token": "90937141|-31948799583822676|90931330",
    "cmd": "PUT",
    "dbName": "SAMPLE",
    "rel": "Emp-Rel",
  	"type":"PUT",
    "jsonStr": {
        "empId":"1",
        "empName": "Sulbha Mishra",
        "empEmail": "sulbhamishra@gmail.com",
    	}
	}
	



## sources:
	   *Net Beans IDE
	   *JPDB  
  
  
