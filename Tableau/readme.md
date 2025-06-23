# Tableau Template Readme

The instructions for configuring the template are below – please download the .TWB file prior to starting the setup process.

## Data Extract Setup (Pre-requisite)
<ol type="1">
<li>Set up and schedule a data extract in your Arena workspace settings 
<ol><li>1x per day is suggested but you can select any recurring period – the template file only loads the latest run of Data Extract </li>
<li>Select the Full extract type - Full is Recommended</li>
<li>Select all available data extract views – the queries will handle any views with no data </li></ol></li>
<li>Select either the "DataExtract CSV" or "RFC 4180 CSV" format – the queries will handle either format </li></ol></li>

<p align="center">
<img src="https://github.com/user-attachments/assets/76f59d84-df51-4f75-a419-ad6bd842ce33"/>
</p>

<li>Starting in Release 2025.2 , there is no longer a DataExtract user profile set up upon creation. You will need to create a machine user profile under Workspace Settings > Employees > Machine Users. For any existing DataExtract setups, the prior DataExtract logins were converted to a Machine User during the release of 2025.2. <b>The Machine User must have the proper Access Policy rules (Read DataExtract under the Workspace Settings sub-tab of a policy) to administer DataExtract (or be granted Arena administrator) in order for it to access the DataExtract endpoints in the API - below is a screenshot of a basic access policy to set up and assign to the Machine User profile in its workspace access.</b> </li>
<img src="https://github.com/user-attachments/assets/a6d4a6a3-6b6a-4ad0-a0bc-7a938aeb487a"/>
<li>Note the Machine User's email and password you generated, as well as the workspace ID. These will be needed for the setup in Tableau.  </li>
</ol>

## Tableau Template File Import and Setup
<ol type="1">
<li>Note the Machine User's email, password, and workspace ID from Step 1<br>
  Note: we are currently developing an enhancement to gracefully handle incorrect user credentials (API result status code: 400). 
  Triple check your credentials if you have any download issues, and wait 5 minutes in case your data extract account gets locked. </li>
<li>If necessary, customer must purchase Tableau from their website. (https://www.tableau.com/pricing/teams-orgs)</li>
  <ol><li> At least 1 required Creator license at $70 per month (per user, billed annually) - other editor ($42) and viewer ($15) licenses are cheaper.</li>
    <li>Customers can only use Tableau Desktop with Tableau Cloud (hosted) or Tableau Server (on-premise or public cloud).</li>
    <li>The free Tableau Public space won't work with the template file. </li></ol>
  
 <li>Open it in Tableau Desktop by doing the following:</li> 
  <ol><li>From the landing page, click File > Open and the selecting the .twb sample file.

&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/Tableau_SS1.png" alt="Arena Analytics">
</p>
&nbsp;</li>
    
  <b>Once the file opens, you will need to log into your Arena workspace. Select the "Data Source" tab in the bottom-left of the screen. This will prompt you to log into Arena with your Data Extract email, password, and workspace ID from Step 1.</b>
   <li>On the next dialog box, enter values for the variables according to your workspace:</li>
         <ol><li>Select your Arena Instance: select the correct API URL for either the North America, GovCloud, or Europe API instance (default: Arena - North America)<br>
        •	https://api.arenasolutions.com/v1 (North America)<br>
        •	https://api.arenagov.com/v1 (AWS GovCloud)<br>
        •	https://api.europe.arenaplm.com/v1 (Europe)</li>
            <li>Arena Email - the REST API User email (ie. The Machine user's email address – see above)</li>
            <li>Arena Password - the Machine User password</li>
            <li>Arena Workspace ID - the workspace ID you want to connect to</li>

&nbsp; 
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/Tableau_SS2.png" alt="Arena Analytics">
</p>
&nbsp;  
   
   <li>Enter your credentials and click "Download Arena Data". The query should take 1-2 minutes (or faster depending on your internet bandwidth).</li>
   <li>Then you can click on the other dashboard tabs along the bottom of the screen to review and customize.</li>
 
&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/Tableau_SS3.png" alt="Arena Analytics">
</p>
&nbsp;

 <li>You can save your own Tableau workbook once finished, and manage that version going forward. You can also publish the data source and dashboards from 
    Tableau Desktop to Tableau Cloud for other Tableau users to reference by using the publishing options under the Server menu. </li>
        </ol>

</ol><br>
  
## 👋 Frequently Asked Questions
Q: I entered my credentials but the query keeps running and is stuck, what should I do?<br>
A: Cancel the query and make sure that you select the Data Source tab in the bottom-left. Sometimes trying to review the report first will not allow the Data Source table/column schema to be defined and a failure occurs during the download that the query screen doesn’t capture. This will hopefully be fixed in a future enhancement to the template. When you click on Data Source, you may have to re-enter credentials, but once the schema is loaded, you will see a list of tables on the left side of the screen and the schema relationships on the main window. 
  Then you should be OK to click on each of the other Arena Dashboard tabs.
<br><br>

Q: I still need help, what should I do?<br>
A: Please contact your Arena Account Manager, Customer Success Coach, or Arena Support and we’ll gladly review your connection issue and get your Tableau environment loaded with your Arena data.

<br>

## Copyright & license

Copyright (c) 2023 Arena, a PTC Business - Released under the [MIT license](LICENSE). Arena Solutions and the Arena Logo are trademarks of PTC, Corporation.
