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
  ![image](https://github.com/user-attachments/assets/978b928a-6cf4-4524-90f6-6eff0c54f931)

  


