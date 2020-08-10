# Lab 100 - Provisioning your Autonomous Database instance

Click on the hamburger **MENU** link at the upper left corner of the page.

This will produce a drop-down menu, where you should select **Autonomous Data Warehouse.**

![Oracle Cloud Web Console](./images/lab100_1.png)

This will take you to the management console page.

To create a new instance, click the blue **Create Autonomous Database** button.

![Oracle Cloud Web Console](./images/lab100_2.png)

Enter the required information and click the **Create Autonomous Database** button at the bottom of the form. For the purposes of this lab, use the information below:

>**Compartment:** Verify that a compartment (*\<tenancy_name\>*) is selected.

By default, any OCI tenancy has a default ***root*** compartment, named after the tenancy itself. The tenancy administrator (default root compartment administrator) is any user who is a member of the default Administrators group. For the lab purpose, you can use ***root***.

You can learn more about compartments in this link:
<https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/managingcompartments.htm>

> **Display Name:** Enter the display name for your ADW Instance. For this demo purpose, I have called my database **ADW_OAC**.
>
> **Database Name:** Enter any database name you choose that fits the requirements for ADW. The database name must consist of letters and numbers only, starting with a letter. The maximum length is 14 characters. You can leave the name provided. That field is not a mandatory one.
>
> **Workload Type:** Autonomous Data Warehouse
>
> **Deployment Type:** Shared Infrastructure
>
> **Always Free:** On

We have selected Always Free Tier On to learn more about this option
check the following link:

<https://www.oracle.com/uk/cloud/free/#always-free>

![Oracle Cloud Web Console](./images/lab100_3.png)

> **Choose Database version:** 19c
>
> **CPU Count:** 1
>
> **Storage Capacity (TB):** 0.02
>
> **CPU Count and Storage Capacity (TB)** are defined by default for the Always Free Tier.
>
> **Auto scaling:** Off

![Oracle Cloud Web Console](./images/lab100_4.png)

Under **Create administration credentials** section:

> **Administrator Password:** Enter any password you wish to use nothing the specific requirements imposed by ADW. A suggested password for this lab is ADWwelcome-1234
>
> ***Reminder:** Note your password in a safe location as this cannot be reset.*

Under **Choose network access** section:

> Leave **'Allow secure access from everywhere'**: *On*
>
> Select **Configure access control rules:** *Off*

![Oracle Cloud Web Console](./images/lab100_5.png)

Under **Choose a license type** section, choose **License Type: Licence Included*.

When you have completed the required fields, scroll down and click on the blue **Create Autonomous Database** button at the bottom of the form:

![Oracle Cloud Web Console](./images/lab100_6.png)

The Autonomous Database Details page will show information about your new instance. You should notice the various menu buttons that help you manage your new instance -- because the instance is currently being provisioned all the management buttons are greyed out.

![Oracle Cloud Web Console](./images/lab100_7.png)

A summary of your instance status is shown in the large box on the left. In this example, the colour is amber and the status is **Provisioning.**

![Oracle Cloud Web Console](./images/lab100_8.png)

After a short while, the status will change to **Available** and the "ADW" box will change colour to green:

![Oracle Cloud Web Console](./images/lab100_9.png)

Once the Lifecycle Status is **Available**, additional summary information about your instance is populated, including workload type and other details.

The provisioning process should take under 5 minutes.

After having the Autonomous Database instance created and available, you can get a message window asking you to upgrade from 18c to 19c if you have selected 18c as a database version during the provisioning. You can
upgrade the database release if you wish after the hands-on session, otherwise the upgrade process can take a few minutes and you can miss a few exercises during the session.

You can now proceed onto running the next labs.

## About Configuring Auto-Scaling in the Autonomous Database - Optional

If you select auto scaling Autonomous Database can use up to three times more CPU and IO resources than specified by the number of OCPUs currently shown in the Scale Up/Down dialog without any manual intervention required. On the  \"*Autonomous Database Details*\" page for your Autonomous Database, click the **Scale Up/Down** button.

![Oracle Cloud Web Console](./images/lab100_10.png)

In an \"Always Free\" tier database in a tenancy with no credits, the *Scale Up/Down* pop up is limited in functionality, as autoscaling requires to go over the CPU and Storage count allowed for Always Free tier.

Mora information about Oracle Always Free Tier:
<https://docs.cloud.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm>

![Oracle Cloud Web Console](./images/lab100_11.png)

In a paid tenancy the \"*Scale Up/Down*\" pop-up will appear as below.

![Oracle Cloud Web Console](./images/lab100_12.png)

Enabling auto-scaling, or manually scaling the Autonomous Database is transparent to running workloads of the system. Only an administrator will be aware of this change in progress when the Lifecycle State changes to \'*Scaling in Progress*\'.

![Oracle Cloud Web Console](./images/lab100_13.png)


## Accessing the Performance Hub - Optional

Performance Hub allows you to examine real-time and historical performance data, view Active Session History (ASH) Analytics and SQL Monitoring.

From your Autonomous Database Details page, select **Performance Hub** from the Action Menu.

![Oracle Cloud Web Console](./images/lab100_14.png)

The Performance Hub page consists of the following regions:

\- The Time Range field and slider

\- Active Session History (ASH) analytics tab

\- SQL Monitoring Tab

You can have different options under this section based on the region and version that you have selected. For more information, check the official [Oracle
documentation.](https://docs.oracle.com/en/cloud/paas/atp-cloud/atpug/monitor-performance-intro.html#GUID-54CCC1C6-C32E-47F4-8EB6-64CD6EDB5938)

Your Performance Hub page may not have any monitored SQL sessions available in the screen now because your instance has been created a few minutes ago. If this is the case, just examine the screenshots and use the menu bars within the Performance Hub to examine what data you could
use.

### The Time Range 

The \"**Time Range Selector**\" is on the top of the Performance Hub page. You can use the \"Select Duration\" field to set the time duration displayed. You can choose to view Last Hour (default), Last 8 hours, Last 24 hours, Last week, or specify a custom time range using the Custom option.

![Oracle Cloud Web Console](./images/lab100_15.png)

The Time Range field shows active sessions in chart form for the time period selected. The active sessions chart displays the average number of active sessions broken down by CPU, User I/O, and Wait. The active sessions chart also shows the Max CPU usage.

### Active Session History (ASH) Analytics 

This shows **Active Session History** (ASH) analytics charts to explore Active Session History data. You can drill down into database performance across multiple dimensions such as Consumer Group, Wait Class, SQL ID, and User Name.

![Oracle Cloud Web Console](./images/lab100_16.png)

### SQL Monitoring 

The SQL statements by default are only monitored if they have been running for at least five seconds or if they have run in parallel.

The table displays the top 100 monitored SQL statement executions, and you can choose to alter the display by dimensions such as Last Active Time, CPU Time, and Database Time. You can also choose to kill badly behaved SQL sessions from this screen.

![Oracle Cloud Web Console](./images/lab100_17.png)