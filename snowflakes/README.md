# Snowflakes on Dashboards and Sites

#### To get this working on dashboards 0 and 1:

- Add a HTML widget  
- Paste in the content of snippet.html  
- Save the dashboard  

#### To update the code so that it works on other dashboards:  

- Locate the line of code towards the end that looks like the following (which makes it appear on the 1st and 2nd dashboards): ```$('.dashboard-1, .dashboard-0').snow({```  
- Update the selector to include the dashboard indexes you wish it to appear on (which makes it appear on the 2nd and 3rd dashboards): ```$('.dashboard-2, .dashboard-1').snow({```  

#### To update the code so it works on an individual site:  

- Open up the site you wish to add this to.  
- Right click the background area of the site and click "Inspect", "Inspect Element", or the relevant one for the developer tools you're using.  
- Of the element highlighted, move up the element tree to the div with a css class "sites-site-container" and which has an attribute named "data-site-uuid".  
- Copy this UUID to a safe place.  
- Locate the line of code in the Snowflakes snippet towards the end that looks like the following: ```$('.dashboard-1, .dashboard-0').snow({```
- Update this to the following code: ```$('[data-site-uuid="<site_UUID>"]').closest('.app-sites').snow({```  
- Replace ```<site_UUID>``` with the actual UUID of the site you copied earlier e.g. ```$('[data-site-uuid="2536CF8B200257BB95BF3F7815CB6C0AF11C124C378A26DB"]').closest('.app-sites').snow({```  