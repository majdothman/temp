#MsCMS
MsCMS is an open source PHP based web content management system. MsCMS is copyright (c) 2018 by [Majd Othman](https://github.com/majdothman).

This document provides a basic introduction to MsCMS.
#
### what do you need?
* Php version 7
* mysql
* composer
* apache server example for local(vagrant [download](https://www.vagrantup.com/)) or with Docker.
#
### Install

    $  git clone https://github.com/majdothman/MsCMS.git your-project

* open index.php in your server ex:(localhost:mscms.com/index.php)
* website root is a folder Web
* You will see >>   MsCMS First Install 


| &nbsp;            | &nbsp;
| -------------     |:-------------
| `Host Name`         | host name ex:(localhost)  
| `Database Name`          | the name of new database    
| `User name `    |  user name of user in mysql server
| ` User Password `              | password of user in mysql server
 
 * click Go to step 2 to end
#
### MsCMS is ready now
1. Log in (email: admin@mscms.com , password: mscms.admin )
    - Change the password of admin From CMS Users (current password is : mscms.admin )
    - then add new admin From CMS Users to use MsCMS
    <p>
      <img src="/test/test.png" width="400" height="auto"/>
    </p>
    
2. Try adding a new category in the Categories to see if everything is fine 
    - you find the Categories in Aside menu     
3. In Aside menu click on 'add new Extension' 
    - here you can create new Extension 
        - Extension name | the name of extension and **table** in DB
        - Title in Aside menu | the name that you will see in menu
    - Fields : These fields will be added to the extension and table
    - Example (Products)
        - every product has name,price,category ...etc
        - so these fields are : **title,content,name,price,category**
    - **Extension Files:**
        - Classes
            - Controller
                - ExtensionController.php > to write your methods and control of your extension 
            - Model
                - Domain
                    - Extension.php > to write properties of class [optional] 
                - Repositories
                    - ExtensionRepositories.php > Works with ExtensionControl to communicate with databases
        - Resources
            - Template (**You can access to this template through <action> in url** )
                - Add.html  > Frontend for add page 
                - Delete.html  > Frontend for delete page
                - Edit.html  > Frontend for edit page
                - Overview.html  > Frontend for Overview page
                - More template   > [optional]  (**You can access to this template through <action> in url** )
                
4. After create new extension you can see it in Aside menu
    - you can add, edit and delete
       
5. See Documentation in Aside menu
 
 #
 ### Should you know
 * Variable Of $GLOBALS:
     
     | Tables                    | Are           
     | -------------             |:-------------
     | `  ['seeError']`          | Exception if you are developer and you want see the Errors 0: NO , 1: Yes
     | ` ['defaultLanguage'] `   | The Default language for Cms 
     | ` ['timeStamp'] `         | time now (integer)
 
     
               
 
* #### Variable Of URL:
 
     | Tables            | Are           
     | -------------     |:-------------
     | `extName`         | The Extension Name  
     | `action`          | the action(method) Name in Controller   

   - **The name of Method in Class Ex:(editProductsAction)**
     
               
* #### Variable to twig in HTML:
 
     | Tables            | Are           
     | -------------     |:-------------
     | `extName`         | The Extension Name  
     | `content Path`    | The path of content in resource <br> Ex:(\mscms\Extensions\Dashboard\Resources\Template\Overflow.html)      
     | `extRepository `  | The Repository of the Extension Ex:(DashboardRepository) <select,unsert,update with DB>
     | `extController `  | The Controller of the Extension Ex:(DashboardController)    
     | `beController`    | The Controller of Backend :BeController
     | `userController`  | The Controller of Users :UserController
     | `box`             | The level and Message in the box ((Success,Error...) & (Message))
     | `  `              | 
     
               
* #### Cookie
        $_COOKIE['userId'] = user id
        $_COOKIE['active'] =  if user loged in

* #### to excute one method in controller you need to " ext and process " Ex:
   URL:  index.php?ext=CmsLanguages&process=methodName
     
     
 
 
 
 
 
 
 
