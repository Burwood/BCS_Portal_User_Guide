<h1>BCS Portal Admin Guide</h1>

**BCS GCP Billing Portal Overview**


The BCS Portal was developed as an enhancement to GCP functionality to address three primary areas: 


* **Budgets:** The ability to define and alert against long-running budgets (as opposed to GCP which only allows monthly budgets to be created, which does not map well to a higher ed environment). Since grant money is often used for GCP, the status of total cumulative spend is typically much more useful than how much is spent each month.  

* **Billing Visibility:** GCP’s Billing Administrator and Viewer roles are assigned at the Billing Account (not Project) level. In an environment where there are many projects within a billing account, there is no way to limit billing detail access at the project level.  Rather, billing viewer has access to all projects within the billing account. The BCS portal provides granular access to information, giving individuals access to just their project's billing info, accessible at any time

* **Current and Past Usage Detail:** SKU-level billing detail is available in the GCP Console only at month-end in the Invoice detail. If a project wants to understand what is driving a spike in GCP consumption totals, that detail is hard to determine using the GCP Console.

* The BCS Portal provides Administrators with:
    * Admin and Project Dashboards to view overall GCP spend or specific project consumption details
    * Project, Budgeting, Alerts, and User configuration capabilities 

There are four functional areas within the GCP Billing Portal:

1. **Dashboards Tab:** Provide snapshot consumption data from GCP. Two dashboards are viewable for users with the Admin role:
    * Admin: dashboard provides data for all projects in the organization (those managed by Burwood, does not include projects in billing accounts not created by Burwood, e.g., user accounts paid for by personal credit cards)
    * Project: dashboard provides individual project-level detail
2. **Reports Tab:** Numerous standard reports available for GCP consumption data insights.

3. **Administration Tab:**  Location for Administrators to view and update information about and control user access to GCP projects in the BCS Portal. Only Administration resources will see this tab.

4. **Cloud Request Tab:** Allows users to submit and check status of GCP Billing service requests.
<br>

<h1>Administration > Projects</h1>

**Project Setup Process**

![chart](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/chart1.PNG)

When a project is created in GCP, a monitoring project (deployed within each billing account by Burwood) publishes consumption data to a GCP BigQuery table.  As soon as there is spend* for a GCP project, it will appear in the BCS Portal under the heading of “Unaffiliated Projects”.  

As a BCS Portal Administrator, you will then enter project metadata (including department alignment, project owner, and billing contact), assign project users, update budget(s), and set alerting thresholds.


**Note:** The project will not be visible in the Project Dashboard until billing against it commences.

<br>

**Project Setup**

<br>

The Administration > Projects tab provides the ability for project administrators to enter pertinent information about GCP projects to ensure they appear accurately and provide the correct information in the BCS GCP Billing Platform.

![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic1.png)

As soon as there is spend for a GCP project, it will appear in the BCS Portal under the heading of “Unaffiliated Projects”.

BCS Portal Administrators will be responsible for updating the following information and activities:
* Defining Department alignment*
* Creating Project Name/Description
* Completing:
    * Primary owner contact info
    * Billing contact info
    * Project Users
* Budget(s) information
* Setting alerting thresholds

*If no department assigned, the project will remain in Unaffiliated Projects

![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic2.png)

To set up Projects:
1. Click on Unaffiliated Projects and select the desired project. The following information will auto-populate from GCP:
    * Project ID
    * Billing Accounts
2. Complete the project related fields
3. To set budgets, click the plus sign to display budget fields. If multiple budgets, click	the plus sign again for additional budget line items.
4. To set Alert Thresholds, click the plus sign to add a threshold slider. For multiple threshold alerts, click the plus sign to add slider.
5. Add Project Users who will have access to project data in the BCS portal. Click on the magnifying glass to select users

<br>

**Project Setup- Alternate Approach**

<br>

If there’s a desire to add a project and set up users in advance of billing in GCP (before the project would be auto-discovered), you can click on Add Project.

To manually set up a Project:
* Copy the Project ID from GCP and populate that field to start the new record
* Continue setup instructions from the previous section

Take care to ensure the Project ID matches what is in GCP exactly – do not use the Project Name from GCP in that field, or data will not correlate!

![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic4.png)

<br>

**Purchase Orders**
<br>

* Customers can create and manage Purchase Order objects that they can use to track and charge back internally.
* There are two types of Purchase Orders: Standard, and Prepaid.
* Standard Purchase Orders are generally not tied to an account.
* Prepaid Purchase Orders are specific to accounts. They can be assigned to Projects and Accounts.
    <br>

**Purchase Order Consumption**

* In the Graph below, the bars in red are Consumption against the Purchase Order. 
* The green shaded bar shows how much budget is left.   
 <br>

![admin-guide-images](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic17.png)

<br>
<br>


**How to add a Purchase Order**
<br>

* Navigate to Administration >Purchase Orders.
    
    <br>
![admin-guide-images](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic18.png)  

<br>

* Next, click on the first box to choose the PO type. Either "Standard" or "Prepaid"
* If choosing prepaid, enter a PO number, the account name, the account number, and the PO amount

<br>

![image19](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic19.png)

<br>

* Click update to save changes.

<![image19](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic20.png)>

<br>

**How to relate a Purchase Order to a Project**

* Now that the new PO has been created, it can be selected when a new Budget Item is added.
* To add a Purchase Order, click the Cost Object field on the budget line item, then  select the appropriate PO to bill against. 



<br>
<![image19](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic21.png)>







<br>


**Project Setup: "After Budget"**

<br>



An important field to understand the functionality behind is “After Budget”:

Selecting “Suspend” for this field means that defining a project budget will limit project spend to the defined budget. Once the budget is consumed, the project will be disabled. (This is accomplished by removing the billing account from the project, preventing additional spend).

Selecting “Bill” for this field means that any budgets added to the project are informational only… no action will be taken to prevent spend beyond the defined budget.


![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic5.png)

<br>

**Alert Threshold Notifications**

<br>

Alert thresholds allow you to identify at which levels of budget consumption you would like to be notified.

Notification will be sent via email to all project users once the current budget reaches the defined threshold. 

To set Alert Thresholds:
* Navigate to Administration | Projects
* Scroll to show Alert Threshold
* Slide Toggles to desired thresholds

**Note:** The Administration page is used by your administrator to set up the parameters of your project(s). Project users can only configure alerts.

![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic6.png)


**Velocity Alerts**
<br>
To set a Velocity Alert:

* Navigate to Administration | Project
* Click the option to add alert
* Check the Velocity Alert box
* Next, enter in the Alert Threshold dollar amount Per Day


<br>

![admin-guide-images](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic16.png)





**Setting Budgets**

<br>

To establish a budget, click on the plus sign next to **Budget Items:**
* **Type:** Will be populated based on the billing account selection
* **Cost Object:** Use this field to record any internal billing number information, if useful for reference
* **Date Issued:** To record when the budget amount was approved.
* **Date Activated:**
    * If Initial budget, use the same date as the Date Issued.
    * If subsequent budget, this field will be auto-populated when the budget becomes active.
* **Account #/Account Name:** Select the billing account used to fund the budget. Choosing one will populate the other.
* **State:** Mark as Active for current budget, Future for subsequent.  
* **Next:** If there are Future budgets, one needs to have the Next radio button enabled to denote order.


![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic7.png)

<br>

**BCS Portal > GCP Automation**

<br>

During client onboarding, Burwood works with our clients to decide what level of automation is desired leveraging the BCS Portal.  

In cases where full automation is desired, budgets are automatically enforced from within the BCS Portal.As soon as a budget limit is exceeded, the portal will trigger an update to GCP as appropriate:

* In cases where there is no subsequent budget and the **After Budget** field is set to **Suspend**, the project will have the billing account removed, resulting in project being put in suspense.
* In cases where there is no subsequent budget and the After Budget field is set to Bill, the portal will communicate to GCP to execute the switch of the project to the billing account configured (See Project Setup: “After Budget”).
* In cases where a subsequent budget is coded to a different Billing Account, the portal will communicate to GCP to execute the switch of the project to the new billing account

<br>

**A Note on Cost Updates and Budgets**

<br>

Google does not have an SLA for how current they keep consumption data within the GCP Console. They claim that spend data may not be final for up to 2 days. In practice, we see data updated within a few hours of the spend occurring.  

The BCS Portal pulls data from GCP every 30 minutes.  

These two factors need to be considered when setting Budgets. If a funded amount is an absolute "do not exceed" value, then the budgeted amount should be reduced in the BCS portal to account for the potential delay in reported spend to stay under that threshold.

<br>

**Departments**
<br>

Departments can be added to group projects together in the portal. There are two types of Departments:
* Reporting
* Budgeting 

**Reporting** departments are used to group projects together to:
* Organize the view on the Administration > Projects tab
* Simplify assigning users to all the projects within a department 

**Budgeting** departments provide the functionality of Reporting departments, and:
* Force budgets to be made at the Department rather than Project level (Projects in that Department share a common budget)

![setup](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic8.png)

<br>

<h1>Administration > Users</h1>

**User Setup**

To set up Users:
1. Click Add User
2. Populate First and Last Name fields
3. Add the email address that will be used as the individual’s login ID for the BCS Portal. If you are configured for Single Sign-on, ensure you use the individual’s official email, not an alias address.
4. Choose the Role and hit Update to save
    * Project User: Individual will have access to billing data for one or more projects, with access granted in the Project User section of Administration > Projects
    * Admin Read-Only: Users have access to view all projects, but can not set budgets or update project information
    * Admin User: Can access and update all projects

![adduser](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic9.png)

<br>

<h1>Dashboards</h1>


**Admin Dashboard Overview**

The Dashboards > Admin tab provides a quick and concise view of consumption and budget details for all projects within the purview of the Administrator.

![admindash](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic10.png)


**Admin Dashboard: Chart Description**

The Admin Dashboard provides a number of charts to track and manage GCP consumption.

![adminchart](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/chart2.PNG)


**Project Dashboard Overview**

The Dashboards > Project tab provides information about project specific budgets and current spend, as well as access to widgets to gather more detail about GCP project related expenses. 

Widgets include:


A. **Project Detail:** Provides basic project information about funding events, total budget, and total consumption.

B. **Dashboard Widgets:** Allows you to view to see Consumption data in a variety of formats.

C. **Control Panel:** Allows you to view or hide Dashboard Charts.

![projdash](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic11.PNG)

**Note:** The BCS Portal Overview provides a detailed review of the Project Dashboard and information available to Project Users.

<br>

**Access to Data via Widget Details**

The Details dropdown in each widget allows you to view additional details about a specific graph:

A. To see a tabular view of the data used to create the graph, click the Details carrot.

B. Data can be exported from this view to:
* Excel
* CSV
* PDF formats

C. Search within the data details

![widget](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic12.PNG)


<h1>Reports</h1>

**Standard Reports**

The GCP Billing Portal provides a numerous reports including:
* Consumption by Time (All Projects)
* Consumption Over Time*
* Service Consumption Over Time*
* Entity Consumption Over Time*
* Consumption by Project 
* Current Budget Status
* Consumption by Entity
* Consumption by Service
* Consumption by Label
* Consumption by Department

*Requires selection of Project for which you want the reporting details

**Note:** New projects will not be visible on budget specific reports until a budget is configured.


![stanreport](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic13.png)

<br>

**Reports Options**

The Reports function provides in-depth metrics and options to allow you to see your data:

A. Customizing time range selection to drill into desired dates

B. Option to view reports based on specific funding source

C. Numerous standard reports that provide detailed breakdown of consumption, services, discounts, etc.

**Note:** The report page is directly integrated with the table, so clicking anything in the report graph will show any relevant info in the table. 

![report](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic14.PNG)

<br> 

**Reports**

To Run reports:

1. Select and/or define the specific criteria for which you plan to run your report: Date Range and Funding Sources
2. Select the desired Standard Report 
3. If required, select the project for which you want the report
4. Click Run

**Note:** You will need to click Run after each criteria or report type change in order to refresh the report.

![reporting](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/admin-guide-images/pic15.png)









