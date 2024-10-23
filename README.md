# TestAutomation
Selenium , SpecFlow , C# 


------ Setup ------
1. Create a new Project (NUnit Project)
2. Install Nuget Packages
   SpecFlow
   SpecFlow.NUnit
   Webdriver Manager
   Selenium Webdriver
   Selenium Support

4. Right click ->  Add an Item ->  SpecFlow Configuration
5. Add "language": {
  "feature": "en-US"
}

6. Right click SpecFLow.json -> Proporities and set Copy to Output Directory to "Copy always"

-----

Lets step up some of our basic feature files for Specflow which uses the Gherkin Language

Login.feature

** NOTE - Sometimes Net 8.0 will give you all steps are already defined when they actually aren't , to resolve this change the Target framework to 6.0 or 7 and then revert back 

---- EXAMPLE -----
Feature: Login

Check login 

@tag1
Scenario: User provides Valid login details 
	Given The user is on the login page
	When The user provides a username
	When The user provides a password
	Then The user is logged in


Next Rebuild and the feature file text should turn purple and no longer back 

Right click Define step and copy to Clipboard -> Create a C# Class and call it Websteps and paste our steps and change it to a public class

Within your websteps -> Create a public Webstep function and define WebDriverManager and IWebdriver 

![image](https://github.com/user-attachments/assets/15c327fa-d85d-486e-8804-c1cded62fe0c)


Next using Selenium, can we navigate to the login page and enter the username+password and click the login button 
![image](https://github.com/user-attachments/assets/c1bbeb21-1e8e-4097-91f0-2959202d6267)


------

Create a Configuration json file

Install Nuget Packages
Microsoft.Extensions.Configuration
Microsoft.Extensions.Configuration.Json
Microsoft.Extensions.Configuration.EnvironmentalVariables

Here you can create a json file to hold Username/Password or any other details for configuration


---- Create a Runner File --- -
You can create a Runner file and use the function BeforeTestRun to create your configuration
![image](https://github.com/user-attachments/assets/d0451a69-333d-40da-a966-707b7b91ca2a)


------  Hooks ---- 

Can be used to perform at different times within our Runner class 
![image](https://github.com/user-attachments/assets/364ec088-bed7-4c29-8a89-12d2a5119f6c)

Or when can use Hooks in our WebSteps 
![image](https://github.com/user-attachments/assets/81d563ce-4524-4eb7-915a-3b4bdfb18847)


--- Exernal Assemblies 

This will allow you to call other projects / user there Websteps

Create a new Project-> install nuget packages -> delete thoses that you dont need as you will be using another projects 
go to Add -> Project Reference and check the project you want to reference
create a specflow.json file and add your stepAssemblie or multiple if you need to 

![image](https://github.com/user-attachments/assets/e1c94eb7-ff29-4f87-a63c-eeb7d417ea6c)

----- Parallel Execution  ----

Ablity to run multiple feature files 

Add new Item to the project -> Assembly infomation file -> add assembly info as seen below
![image](https://github.com/user-attachments/assets/dd6c74f5-4235-410b-85e7-a80d54719455)


NUnit

-------



