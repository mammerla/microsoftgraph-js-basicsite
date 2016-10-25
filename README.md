This is a very basic website that uses Microsoft Graph in some simple ways.  This is basically a "hello 
world" Microsoft Graph site that shows you how to get started with Microsoft Graph.

## Outline

This is a paste-in-code demo where we'll show how easy it is to create a Microsoft Graph powered website.
We'll start by creating an Azure Active Directory app registration, update index.html, and see the site.

## Provision your Azure Active Directory tenancy

1. Navigate to the Azure Portal (https://manage.windowslive.com)
2. On the left-hand side, select "Active Directory"

If you haven't already, associate your Office 365 developer/test tenancy with your Azure account
    2a. Select new 
    2b. Select Directory
    2c. Select Custom Create
    2d. In the dialog, select "Use existing directory"
    2e. Select "I am ready to be signed out now", and click Go.  Then, sign into your Office 365 dev/test account

    NOTE! you should only do this with a dev/test O365 account

3. Select your O365 tenancies' Active Directory
4. Select Applications
5. Select Add
6. Select "Add an application my organization is developing"
7. Give it a name, ensure "Web Application" is still selected.
8. Give it a sign on URL that your website is using (e.g. http://localhost:1414)
   You may need to run the website first to know what port you are using.
9. Give it a unique URI of https://<yourtenancyname>.onmicrosoft.com/testappname

Add Permissions:

10.    Selec "Add Application", then select "Microsoft Graph".  
11.  Add  "Sign in an read user profile", 
          "Read all users' basic profiles", 
          "Read all users' full profiles", 
          "View users' email address", 
          "View users basic profile" permissions.
12. Select Manage Manifest / Download Manifest
13. Edit the downloaded manifest.json and set:

  "oauth2AllowImplicitFlow": true,

14. Re-upload manifest.json


Now, go to BasicSite/wwwroot/index.html, and update the client ID and tenancy to match your tenancy name and the 
client ID you've used.

Now run the site.  You should be able to sign in, and then see basic details about users in your tenancy.


