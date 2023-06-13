# PowerBI Template Readme

The instructions for configuring the template are below – please download the .PBIT file prior to starting the setup process.

## Data Extract Setup (Pre-requisite)
<ol type="1">
<li>Set up a data extract scheduled setup in your Arena workspace settings 
<ol><li>1x per day is suggested but you can select any recurring period – the template file only loads the latest run of Data Extract </li>
<li>Select the Full extract type </li>
<li>Select all available data extract views – the queries will handle any views with no data </li></ol></li>

&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/Arena_Analytics_SS.png" alt="Arena Analytics">
</p>
&nbsp;

<li>Note the data extract email, password, and workspace ID from Step 1 </li></ol>

## Power BI Template File Import and Setup
<ol type="1">
<li>Download and open MS Power BI Desktop - <a href="https://www.microsoft.com/en-us/download/details.aspx?id=5849">Latest location here</a></li>
  <li>Open it in PowerBI Desktop by doing the following</li>
  <ol><li>Open other reports (Browse):</li>

&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/PowerBI_SS1.png" alt="Arena Analytics">
</p>
&nbsp;
   
<li>In the browse window, change file type dropdown from Power BI Files (*.pbix) to Power BI templates Files (*.pbit)</li>
 
&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/PowerBI_SS2.png" alt="Arena Analytics">
</p>
&nbsp;

  <li>Locate the provided “Arena Power BI Template[…] .pbit” file and click Open.</li>
  </ol>
  
<li>On the next dialog box, enter values for the variables according to your workspace:</li>
    <ol><li>Arena API URL (var_api_url) - select the correct REST API URL for either the North America, GovCloud, or Europe API instance (default: North America) <br>
      •	https://api.arenasolutions.com/v1 (North America)<br>
•	https://api.arenagov.com/v1 (AWS GovCloud)<br>
•	https://api.europe.arenaplm.com/v1 (Europe)</li>
      <li>Arena Email (var_email) - the REST API User email (ie. Data Extract setup email address – see above)</li>
      <li>Arena Password (var_password) - the REST API User password</li>
      <li>Arena Workspace ID (var_workspace_id) - the workspace ID you want to connect to</li></ol>
      
&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/PowerBI_SS3.png" alt="Arena Analytics">
</p>
&nbsp;

<li>A refresh progress box will appear as Power BI connects to Arena REST API and downloads and extracts the CSV data for each of the Data Extract files. <br>
  Note: On the initial connection to the Arena API, you might get a pop-up dialog box that asks you to get the permission level for the connection. 
  Make sure you select “Anonymous” for the Authentication Type, and select “Organizational” for the Privacy Level. Click OK to continue. </li>
  
&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/PowerBI_SS4.png" alt="Arena Analytics">
</p>
&nbsp;

<li>Once the refresh progress box disappears, the sample reports will be populated with data from the Arena workspace.</li>
  
&nbsp;
<p align="center">
    <img src="https://github.com/ptc-arena/.github/blob/main/PowerBI_SS5.png" alt="Arena Analytics">
</p>
&nbsp;

<li>The Power BI developer can then review and tweak anything in the file (reports, charts, fields, filters, etc.) and then save the result to their own .PBIX file (via File > Save As).</li>

<li>(Optional) If there are any changes to the Data Extract service or to load fresh data updates that happen in Arena, 
  the user can run the Refresh button on the top of the Home tab at any time. The process will run similar to the initial query in Step 4.</li>

</ol><br>
  
## 👋 Frequently Asked Questions
Q: I got an error during the initial setup regarding One to Many relationships, what should I do?<br>
A: While we make every attempt to test our Arena template file in many different types of customer workspaces, there may be an issue where there is one or more duplicate rows that are linked between tables. Typically, the predefined relationships help to link different tables/reports when a user selects a metric in a report. 
To address this, review the error details in the refresh dialog box, noting the table and the column that is specified. Open the ‘Manage Relationships’ menu in Power BI and delete the relationship rows that correspond to that table and column. Once you delete these rows, close and try to refresh data again.
<br><br>

Q: I got a pop-up that asks for permissions for the Arena URL, what should I do?<br>
A: It can happen on the initial connection within Power BI and will be saved for future refreshes of the data. Make sure you select “Anonymous” for the Type, and select “Organizational” for the Privacy Level. Click OK to continue.
<br> <br>
Q: I still need help, what should I do?<br>
A: Please contact your Arena Account Manager, Customer Success Coach, or Arena Support and we’ll gladly review your connection issue and get your Power BI environment loaded with your Arena data.

<br>

## Copyright & license

Copyright (c) 2023 Arena, a PTC Business - Released under the [MIT license](LICENSE). Arena Solutions and the Arena Logo are trademarks of PTC, Corporation.
