<h1>Burwood Cloud Portal User Guide</h1>

<br>
<h3>Table of Contents</h3>
<h4 ng-click="vm.scrollTo('portal overview')" style="cursor:pointer">-Portal Overview</h4> 
<h4 ng-click="vm.scrollTo('dashboards')" style="cursor:pointer">- Dashboards</h4> 
<h4 ng-click="vm.scrollTo('Reports')" style="cursor:pointer">- Reports</h4> 
<h4 ng-click="vm.scrollTo('Updating Threshold Alerts')" style="cursor:pointer">- Threshold Alerts</h4> 



<br>




**Purpose of the Portal** 

The Burwood Cloud GCP Billing Portal was developed as an enhancement to GCP functionality to address three primary concerns:
* The ability to define and alert against long-running budgets, as opposed to GCP which only allows monthly budgets to be created; which does not map well to a higher ed environment, where grant money is often used for GCP and the status of spending over time against the total grant is much more interesting than how much is spent each month.
  
* In an environment where there are MANY projects within a billing account, there is no way within GCP to limit billing detail access at the project level.  Rather, billing viewer has access to all projects within the billing account.  The portal provides individuals with billing info for their project only.

* SKU-level billing detail is available in the GCP Console only at month-end in the Invoice detail.  If a project wants to understand what is driving a spike in GCP consumption totals, that detail is hard to determine using the GCP Console.
<br>

**Project Setup Process**

![process](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/chart1.PNG)

When a project is created in GCP, a monitoring project (deployed within each billing account by Burwood) publishes consumption data to a GCP BigQuery table.  As soon as there is spend for a GCP project, it will appear in the BCS Portal.  Your BCS Portal Administrator will then enter additional metadata, including assigning project users, budget data, and setting alert thresholds.

The project will not be visible in the Project Dashboard until billing against it commences.

<br>

<h1 id='portal overview'>Portal Overview</h1>
<br>

There are four functional areas within the Burwood Cloud GCP Portal:

**Dashboards Tab:** Provides snapshot consumption data from GCP 
* Project dashboard provides individual project-level detail

**Reports Tab:** Numerous standard reports available for GCP consumption data insights

**Administration Tab:** Location for Administration resources to view and provide additional information about all GCP projects. From this tab, Admin users are able to add project metadata and assign users to projects. Project user can see their project in the Administration tab but can only update Alert settings.

**Cloud Request Tab:** Allows users to submit new Cloud Requests

<br>

**Logging In**
<br>

Once access is setup, new users will log onto Burwood Cloud GCP Billing Portal at: https://bcs.burwood.com/cloudbilling_dashboard

Log on in two different ways:
* Your email and password
* If SSO is enabled, select "Sign-In With SSO" and use your email address. 

![SSO](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic1.png)

<br>

<h1 id='dashboards'> Project View: Dashboards </h1>

**Project View: Burwood Cloud Portal Overview**

Upon log in, the Project dashboard is displayed, with  information about budgets and current spend, as well as access to widgets to gather more detail about GCP project related expenses. 

Widgets include:


A. Project Details: Provides basic project information about funding events, total budget, and total consumption


B. Dashboard Widgets: Allows you to view to see Consumption data in a variety of formats


C. Control Panel: Allows you to view or hide Dashboard Charts

![ProjectView](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/projectview.PNG)

<br>

**Project View: Project Details**

Basic project information related to funding events, total budget, and total consumption can be found in the Project Details widget.

If you have access to multiple projects, use the drop-down arrow to select the project for which would like to see the specific details. 

![projectdetails](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic3.png)

| Term                       | Definition                                                                                                                                                                                                                 |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| After Budget               | Provides directions regarding payment option for average amount Bill: Project is allowed to spend without a defined budget Suspend: Project will be disabled once budgets are consumed                                     |
| Type                       | Credit: Funding is via Credits Paid: Consumption will resulting in an invoice                                                                                                                                              |
| State                      | Active: Allowance against which project is currently being billing Consumed: A budget that has been fully used up Future: A budget established to fund future charges - will become Active once current budget is consumed |
| Issued                     | Date budget was formalized                                                                                                                                                                                                 |
| Activated                  | Date that project spend started consuming the individual budget allowance                                                                                                                                                  |
| Current Budget Consumption | Current spend against the active budget                                                                                                                                                                                    |
| Current Budget Remaining   | Amount remaining in the active budget                                                                                                                                                                                      |
| Total Consumption          | Includes all spend for all budgets since project was created                                                                                                                                                               |
| Total Budget               | Total of past, current and future budget                                                                                                                                                                                   |

<br>

**Project Details: Budget Consumption Calculations Example**

![calculations](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/calc.PNG)

A. Current Budget Consumption: Amount spent against the Active budget


    A(n) = Allowance for budget number (n)


	S(n) = Spend against A(n)

B. Current Budget Remaining:  Budget remaining for the Active budget 


    Current Budget Remaining = A3 – S3


C. Total Consumption: All spend for all budgets since project was created 


    Total Consumption = S1 + S2 + S3


D. Total Budget: Total of Consumed, Active, and Future budgets


    Total Budget = A1 + A2 + A3


<br>

**Project View: Dashboard Widgets**


The Dashboard widgets display consumption details by multiple factors. 

Available Dashboard Widgets include:
* Consumption by Entity
* Consumption by Service
* Monthly Consumption
* Consumption over Time
* Service Consumption Over Time
* Entity Consumption Over Time

**Note:** Dashboard widgets may be updated, removed, or replaced periodically based on user requests

![widgets](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic5.png)

<br>

**Project View: Service and Entity Consimption**

These widgets provide a detailed view of spend by what has been used within GCP. 

Services are at the high level (e.g., Compute Engine, Cloud Storage, etc.) 

Entities include each specific component (e.g., Nvidia Tesla P100 GPU running in Americas, Storage PD Capacity).  

Views are available over type:
* Consumption by Service
* Consumption by Entity

![service](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic6.png)

and by time:
* Service Consumption Over Time
* Entity Consumption Over Time

![entity](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic7.png)

<br>

**Project View: Dashboard Chart Options**

Where appropriate, dashboard data can be displayed to show the data by different criteria including:

A. Graph Type

As appropriate, the data can be viewed by:
* Line 
* Pie 
* Bar

B. Timeline
* This Month – view current month’s data
* Last 3 Months – view previous 3 months’ data

Changing the timeline view for one widget will change the timeline view for all other dashboard widgets
 
C. The click and drag to zoom function provides the ability to dive deeper into the chart details, such as drilling into a specific date.

![dashchart](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic8.PNG)

<br>

**Project View: Downloading Charts**

Clicking on the menu options provides several options for viewing and downloading the chart view:

* Download PNG image
* Download JPEG image
* Download PDF document
* Download SVG vector image

![downloadingcharts](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic9.png)

<br>

**Project View: Dashboard Widget Detail**

The Details widget allows you to view additional details about a specific graph:

A. To see a tabular view of the data used to create the graph, click the Details carrot.

B. Data can be exported from this view to:
* Excel
* CSV
* PDF formats

C. Search within the data details

![dashwidget](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic10.png)

<br>

<h1> Reports </h1>

<br>

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

![standardreport](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic11.png)

<br>

**Reporting**

To Run reports:

1. Select and/or define the specific criteria for which you plan to run your report: Date Range and Funding Sources
2. Select the desired Standard Report 
3. If required, select the project for which you want the report
4. Click Run

**Note:** You will need to click Run after each criteria or report type change in order to refresh the report

![reports](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic12.png)

<br>

<h1> Updating Threshold Alerts</h1>

Alert thresholds allow you to identify at which levels of budget consumption you would like to be notified.

Notification will be sent via email to all project users once the current budget reaches the defined threshold.

To set Alert Thresholds:
1. Navigate to Administration | Projects
2. Scroll to show Alert Threshold
3. Slide Toggles to desired thresholds

**Note:** The Administration page is used by your administrator to set up the parameters of your project(s). Project users can only configure alerts.

![alerts](https://github.com/Burwood/BCS_Portal_User_Guide/raw/main/user-guide-images/pic13.png)

