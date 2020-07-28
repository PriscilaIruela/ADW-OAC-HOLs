
# Oracle Autonomous Data Warehouse and Oracle Analytics Cloud Hands on Lab Guide

![](media/image2.jpg){width="8.259842519685039in"
height="4.1299212598425195in"}

Table of Contents

[1 Lab Introduction 3](#lab-introduction)

[1.1 Lab technical requirement 3](#lab-technical-requirement)

[2 Getting Started 4](#getting-started)

[2.1 Lab 000 - Creating and connecting to your Oracle Cloud Free Tier
Account
4](#lab-000---creating-and-connecting-to-your-oracle-cloud-free-tier-account)

[2.2 Lab 100 - Provisioning your Autonomous Database instance
7](#lab-100---provisioning-your-autonomous-database-instance)

[2.2.1 About Configuring Auto-Scaling in the Autonomous Database -
Optional
12](#about-configuring-auto-scaling-in-the-autonomous-database---optional)

[2.2.2 Accessing the Performance Hub - Optional
14](#accessing-the-performance-hub---optional)

[2.3 Lab 200 - Provisioning your Oracle Analytics Cloud (OAC) instance
16](#lab-200---provisioning-your-oracle-analytics-cloud-oac-instance)

[2.4 Lab 300 - Using Oracle Analytics Cloud (OAC)
22](#lab-300---using-oracle-analytics-cloud-oac)

[2.4.1 Create the connection from Oracle Analytics Cloud to Autonomous
Database
22](#create-the-connection-from-oracle-analytics-cloud-to-autonomous-database)

[2.4.2 Prepare the dataset 29](#prepare-the-dataset)

[2.4.3 Create Visualizations using your data sets
34](#create-visualizations-using-your-data-sets)

[Appendix A - Provisioning an Oracle Analytics Cloud Instance
58](#appendix-a---provisioning-an-oracle-analytics-cloud-instance)

[Want to learn more about ADW & OAC?
64](#want-to-learn-more-about-adw-oac)

Lab Introduction
================

In this hands-on lab, you will get first-hand experience of using Oracle
Cloud, Oracle Autonomous Database (ADB) and Oracle Analytics Cloud
(OAC).

Oracle Autonomous Database (ADB) delivers a self-driving, self-securing,
self-repairing database service that can instantly scale to meet
demands. The service supports two workload types:

-   Oracle Autonomous Data Warehouse (ADW) provides an autonomous
    warehousing environment, associated with fast query performance.

-   Oracle Autonomous Transaction Processing (ATP) provides an
    autonomous online transaction processing and mixed workload
    environment.

For the purpose of this lab, we will use ADW so all the steps will be
related to this database service.

Oracle Analytics Cloud (OAC) is a scalable and secure public cloud
service that provides a full set of capabilities to explore and perform
collaborative analytics for you, your workgroup, and your enterprise.

With Oracle Analytics Cloud, you also get flexible service management
capabilities, including fast setup, easy scaling and patching, and
automated lifecycle management.

To run the lab, you will need an Oracle Free Tier Account, with a
provisioned ADW instance and a a provisioned OAC instance. This
pre-requisite guide will take you step-by-step through how to get the
account and set the instance up, to be ready to start the lab.

Lab technical requirement
-------------------------

This lab requires you to install the following desktop applications so
that you can complete this hands-on lab:

-   PDF File reader.

-   A web browser. The lab guide was created using Google Chrome.

As you will be registering for services in Oracle Cloud, you will also
need:

-   Access to the email account used to register for the workshop.

-   A cell phone to receive an SMS for account verification processes.

Getting Started
===============

This section of the lab will take you through all the required
preparation steps. You will:

-   Lab 000 - Creating and connecting to your Oracle Cloud Free Tier
    account.

-   Lab 100 - Provisioning your Autonomous Database instance.

-   Lab 200 - Provisioning your Oracle Analytics Cloud (OAC) instance.

Lab 000 - Creating and connecting to your Oracle Cloud Free Tier Account
------------------------------------------------------------------------

During this workshop, you will use an Oracle Cloud Free Tier Account to
run the Lab exercises. This account will give you access to the Always
Free resources in Oracle Cloud Free Tier and a limited time trial period
with an expanded set of services. Once this period elapses, you can
continue to use the Always Free resources with no interruptions.

Always Free and Free Trial instances can be seamlessly upgraded to pay
at any time. Existing Oracle Cloud customers have access to Always Free
services automatically---no new sign up required.

To learn more about Oracle Cloud Always Free and Free Trial account
check the following link:

<https://www.oracle.com/cloud/free/#always-free>

As part of your sign up to this lab, you will have been provided a link
to sign up to Oracle Cloud Free Tier. Please make sure you:

-   Use the following URL - [Sign Up for Oracle
    Cloud](https://myservices.us.oraclecloud.com/mycloud/signup?language=en&sourceType=undefined&sourceType=:ow:evp:cpo:::RC_WWMK200720P00081:OER400073848&intcmp=:ow:evp:cpo:::RC_WWMK200720P00081:OER400073848)

-   Use a **[personal email address]{.ul}** that you will use during all
    the workshop process.

On the sign up page, enter your email address, select your
Country/Territory and click \"Next\".

![](media/image3.png){width="3.5576924759405073in"
height="2.899212598425197in"}

On the *\"Enter Account Details\"* page you will be asked for ***Account
Type*,** please select *Company Use* or *Personal Use* considering the
purpose of this cloud account.

You will also be asked for the Cloud Account Name (also known as Tenancy
Name). This will uniquely identify your cloud account and will be
visible in your URL later, so please choose wisely.

Finally, you will be asked also for the \"Home Region\". This is the
location of the physical datacenter. You should select a datacenter that
is geographically close to you and supports the required services. For
this lab, select either UK South (London) or Germany Central
(Frankfurt). This is because Oracle Analytics Cloud (OAC) is currently
only available in UK South (London) and Germany Central (Frankfurt). You
can review which services are available in each region using this page:

<https://www.oracle.com/uk/cloud/data-regions.html#emea>

![](media/image4.png){width="3.760813648293963in"
height="2.4605325896762906in"}

Complete all other mandatory fields on the form (indicated with a \*)
and select **next**. **Verify Your Mobile Phone Number**.

You will be prompted to enter the code sent to your cell phone.

![](media/image5.png){width="3.836538713910761in"
height="3.04576334208224in"}

At the end of this process, you will receive an email titled \"Get
Started Now with Oracle Cloud\". This will contain all the information
you need to sign into your cloud account and include a link to the login
page for your region.

To login to your cloud account, use the same email address that you used
for registration and the password provided in the email. You will be
prompted to set a new, more memorable password.

![](media/image6.png){width="5.7615387139107614in"
height="3.200418853893263in"}

![](media/image7.png){width="6.268055555555556in"
height="2.8835739282589676in"}

Lab 100 - Provisioning your Autonomous Database instance
--------------------------------------------------------

Click on the hamburger **MENU** link at the upper left corner of the
page.

This will produce a drop-down menu, where you should select **Autonomous
Data Warehouse.**

![](media/image8.png){width="3.1458333333333335in"
height="5.989583333333333in"}

This will take you to the management console page.

To create a new instance, click the blue **Create Autonomous Database**
button.

![](media/image9.png){width="2.625in" height="1.4563757655293088in"}

Enter the required information and click the **Create Autonomous
Database** button at the bottom of the form. For the purposes of this
lab, use the information below:

> **Compartment:** Verify that a compartment (*\<tenancy_name\>*) is
> selected.

By default, any OCI tenancy has a default ***root*** compartment, named
after the tenancy itself. The tenancy administrator (default root
compartment administrator) is any user who is a member of the default
Administrators group. For the lab purpose, you can use ***root***.

You can learn more about compartments in this link:
<https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/managingcompartments.htm>

> **Display Name:** Enter the display name for your ADW Instance. For
> this demo purpose, I have called my database **ADW_OAC**.
>
> **Database Name:** Enter any database name you choose that fits the
> requirements for ADW. The database name must consist of letters and
> numbers only, starting with a letter. The maximum length is 14
> characters. You can leave the name provided. That field is not a
> mandatory one.
>
> **Workload Type:** Autonomous Data Warehouse
>
> **Deployment Type:** Shared Infrastructure
>
> **Always Free:** On

We have selected Always Free Tier On to learn more about this option
check the following link:

<https://www.oracle.com/uk/cloud/free/#always-free>

![](media/image10.png){width="6.268055555555556in"
height="3.4722222222222223in"}

> **Choose Database version:** 19c
>
> **CPU Count:** 1
>
> **Storage Capacity (TB):** 0.02
>
> **CPU Count and Storage Capacity (TB)** are defined by default for the
> Always Free Tier.
>
> **Auto scaling:** Off

![](media/image11.png){width="6.268055555555556in" height="1.61875in"}

Under **Create administration credentials** section:

> **Administrator Password:** Enter any password you wish to use noting
> the specific requirements imposed by ADW. A suggested password for
> this lab is ADWwelcome-1234
>
> ***Reminder:** Note your password in a safe location as this cannot be
> reset.*

Under **Choose network access** section:

> Leave **'Allow secure access from everywhere'**: *On*
>
> Select **Configure access control rules:** *Off*

![](media/image12.png){width="6.268055555555556in"
height="1.9826388888888888in"}

Under **Choose a license type** section, choose **License Type:**
*Licence Included*.

When you have completed the required fields, scroll down and click on
the blue **Create Autonomous Database** button at the bottom of the
form:

![](media/image13.png){width="6.268055555555556in"
height="0.9208333333333333in"}

The Autonomous Database Details page will show information about your
new instance. You should notice the various menu buttons that help you
manage your new instance -- because the instance is currently being
provisioned all the management buttons are greyed out.

![](media/image14.png){width="5.925891294838145in"
height="2.521096894138233in"}

A summary of your instance status is shown in the large box on the left.
In this example, the colour is amber and the status is **Provisioning.**

![](media/image15.png){width="1.4780030621172353in" height="1.59375in"}

After a short while, the status will change to **Available** and the
"ADW" box will change colour to green:

![](media/image16.png){width="1.5113659230096237in"
height="1.604121828521435in"}

Once the Lifecycle Status is **Available**, additional summary
information about your instance is populated, including workload type
and other details.

The provisioning process should take under 5 minutes.

After having the Autonomous Database instance created and available, you
can get a message window asking you to upgrade from 18c to 19c if you
have selected 18c as a database version during the provisioning. You can
upgrade the database release if you wish after the hands-on session,
otherwise the upgrade process can take a few minutes and you can miss a
few exercises during the session.

You can now proceed onto running the next labs.

### About Configuring Auto-Scaling in the Autonomous Database - Optional

If you select auto scaling Autonomous Database can use up to three times
more CPU and IO resources than specified by the number of OCPUs
currently shown in the Scale Up/Down dialog without any manual
intervention required. On the \"*Autonomous Database Details*\" page for
your Autonomous Database, click the **Scale Up/Down** button.

![](media/image17.png){width="5.875in" height="0.4166666666666667in"}

In an \"Always Free\" tier database in a tenancy with no credits, the
*Scale Up/Down* pop up is limited in functionality, as autoscaling
requires to go over the CPU and Storage count allowed for Always Free
tier.

Mora information about Oracle Always Free Tier:
<https://docs.cloud.oracle.com/en-us/iaas/Content/FreeTier/freetier.htm>

![](media/image18.png){width="6.268055555555556in"
height="1.8423611111111111in"}

In a paid tenancy the \"*Scale Up/Down*\" pop-up will appear as below.

![](media/image19.png){width="6.268055555555556in"
height="2.435416666666667in"}

Enabling auto-scaling, or manually scaling the Autonomous Database is
transparent to running workloads of the system. Only an administrator
will be aware of this change in progress when the Lifecycle State
changes to \'*Scaling in Progress*\'.

![](media/image20.png){width="1.6826924759405075in"
height="1.8229166666666667in"}

###  {#section .list-paragraph}

### Accessing the Performance Hub - Optional

Performance Hub allows you to examine real-time and historical
performance data, view Active Session History (ASH) Analytics and SQL
Monitoring.

From your Autonomous Database Details page, select **Performance Hub**
from the Action Menu.

![](media/image17.png){width="5.875in" height="0.4166666666666667in"}

The Performance Hub page consists of the following regions:

\- The Time Range field and slider

\- Active Session History (ASH) analytics tab

\- SQL Monitoring Tab

You can have different options under this section based on the region
and version that you have selected. For more information, check the
official [Oracle
documentation.](https://docs.oracle.com/en/cloud/paas/atp-cloud/atpug/monitor-performance-intro.html#GUID-54CCC1C6-C32E-47F4-8EB6-64CD6EDB5938)

Your Performance Hub page may not have any monitored SQL sessions
available in the screen now because your instance has been created a few
minutes ago. If this is the case, just examine the screenshots and use
the menu bars within the Performance Hub to examine what data you could
use.

#### The Time Range 

The \"**Time Range Selector**\" is on the top of the Performance Hub
page. You can use the \"Select Duration\" field to set the time duration
displayed. You can choose to view Last Hour (default), Last 8 hours,
Last 24 hours, Last week, or specify a custom time range using the
Custom option.

![](media/image21.png){width="6.268055555555556in"
height="1.3395833333333333in"}

The Time Range field shows active sessions in chart form for the time
period selected. The active sessions chart displays the average number
of active sessions broken down by CPU, User I/O, and Wait. The active
sessions chart also shows the Max CPU usage.

#### Active Session History (ASH) Analytics 

This shows **Active Session History** (ASH) analytics charts to explore
Active Session History data. You can drill down into database
performance across multiple dimensions such as Consumer Group, Wait
Class, SQL ID, and User Name.

![](media/image22.png){width="6.268055555555556in"
height="2.5743055555555556in"}

####  {#section-1 .list-paragraph}

#### SQL Monitoring 

The SQL statements by default are only monitored if they have been
running for at least five seconds or if they have run in parallel.

The table displays the top 100 monitored SQL statement executions, and
you can choose to alter the display by dimensions such as Last Active
Time, CPU Time, and Database Time. You can also choose to kill badly
behaved SQL sessions from this screen.

![](media/image23.png){width="6.268055555555556in"
height="1.7152777777777777in"}

Lab 200 - Provisioning your Oracle Analytics Cloud (OAC) instance
-----------------------------------------------------------------

There are currently two methods of deploying OAC instances. This section
describes the process of deploying Oracle Analytics Cloud instances on
Oracle Cloud Infrastructure Gen 2, which is the default for newly
provisioned accounts in EMEA and US. If you want to deploy using the
legacy method or Oracle Cloud Infrastructure Gen 1, please see Appendix
A.

Your Oracle Cloud Free Tier account will use the Oracle Cloud Free Trial
credits while this instance is provisioned, as Oracle Analytics Cloud is
not part of the Always Free cloud services.

Provisioning an Oracle Analytics Cloud instance can take over 40
minutes.

Return to the Oracle Cloud Infrastructure Console accessing from
**Oracle Home Page** (oracle.com) and sign in into your cloud account.
Click in **View Account** and **Sign in to Cloud**.

![](media/image24.png){width="6.268055555555556in"
height="0.8534722222222222in"}

Click on the menu icon on the left. Verify that you are signed in as a
Single Sign On (Federated user) user by selecting the **Profile** icon
in the top right hand side of your screen. If your username is shown as:

oracleidentitycloudservice / \<your username\>

Then you are connected as a Single Sign On user.

![](media/image25.png){width="5.041666666666667in"
height="3.1770833333333335in"}

If your username is shown as:

\<your username\>

Then you are not signed in as an Oracle Cloud Infrastructure user.

![](media/image26.png){width="4.6875in" height="3.2291666666666665in"}

If your user does not contain the identity provider --
(oracleidentitycloudprovider), please logout and select to authenticate
using Single Sign On.

![](media/image27.png){width="6.268055555555556in"
height="3.4402777777777778in"}

To be capable of using Oracle Analytics Cloud we need to be Sign-On as a
Single Sign-On (SSO) user.

More information about federated users:
<https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/usingscim.htm>

Return to the *Home Console Page* and navigate to **Analytics** under
**Solutions and Platform** section and then **Analytics Cloud**.

![](media/image28.png){width="4.138194444444444in"
height="3.015277777777778in"}

***Note**: You must be connected as a Single Sign On (Federated user)
user to a tenancy, which has available cloud credits to see this menu
item. Local OCI users are not able to do this.*

Select **Create Instance**.

Complete the form using the following information:

**Compartment**: Select a valid compartment in your tenancy.

**Instance Name**: WORKSHOPADWOAC

**Description**: \<optional\>

**Feature Set**: Enterprise Analytics (important)

**Capacity**: 1 - Non Production

> **License Type**: \"Subscribe to a new Analytics Cloud software
> license and the Analytics Cloud.\" (You will use this service as part
> of the free Oracle Cloud trial that you requested for this workshop).

Select **Create**.

![](media/image29.png){width="6.268055555555556in" height="3.23125in"}

On the Confirmation screen, select **Create**.

The Analytics instance page will be displayed with a status of
*CREATING*.

![](media/image30.png){width="6.268055555555556in"
height="3.6756944444444444in"}

***Reminder***: Provisioning an Oracle Analytics Cloud instance can take
over 40 minutes.

The Analytics instance page will be displayed with a status of *ACTIVE*.

![](media/image31.png){width="6.268055555555556in" height="3.41875in"}

You can now proceed onto running the labs.

Lab 300 - Using Oracle Analytics Cloud (OAC)
--------------------------------------------

Oracle Analytics Cloud provides the industry's most comprehensive cloud
analytics in a single unified platform, including everything from
self-service visualization and powerful inline data preparation to
enterprise reporting, advanced analytics, and self-learning analytics
that deliver proactive insights.

You are going to use an Oracle Analytics Cloud instance to give your end
users a self-service approach to analysing the data.

In this lab, you will:

-   Create a connection from Oracle Analytics Cloud to Autonomous
    Database.

-   Prepare the dataset.

-   Create Visualizations to analyse the data.

### Create the connection from Oracle Analytics Cloud to Autonomous Database

Oracle Autonomous Database only accepts secure connections to the
database. This requires a *\'wallet\'* file that contains the SQL\*NET
configuration files and the secure connection information. Wallets are
used by client utilities such as SQL Developer, SQL\*Plus etc. For this
lab, you will use this same wallet mechanism to make a connection from
OAC to the Autonomous Database.

***Note**: This section assumes you have already created your Oracle
Analytics Cloud instance as part of the 'Lab 200 - Provisioning your
Oracle Analytics Cloud (OAC) instance\' section. If not, please return
to the beginning of Lab200 and go through the instance creation.*

#### Download your Autonomous Database wallet

You need first to download the wallet file containing your credentials.
There are two types of wallet:

-   Instance Wallet: Wallet for a single database only; this provides a
    database-specific wallet.

-   Regional Wallet: Wallet for all Autonomous Databases for a given
    tenant and region (this includes all service instances that a cloud
    account owns).

***Note**: Oracle recommends you provide a database-specific wallet,
using Instance Wallet, to end users and for application use whenever
possible. Regional wallets should only be used for administrative
purposes that require potential access to all Autonomous Databases
within a region.*

In the Oracle Console Home Page, click on the hamburger **MENU** link at
the upper left corner of the page and go to the **Autonomous Data
Warehouse** section.

![](media/image8.png){width="3.1458333333333335in"
height="5.989583333333333in"}

You can see all the ADW instances that you have created.

![](media/image32.png){width="6.268055555555556in"
height="1.2118055555555556in"}

**Select** the ADW instance that we created before.

On the \"*Autonomous Database Details*\" page for your Autonomous
Database, click the **DB Connection** button.

You can access to the '*Autonomous Database Details*' page using the
cloud console page.

![](media/image33.png){width="6.268055555555556in"
height="2.0104166666666665in"}

This will open a pop-up window. Select Wallet Type **Instance Wallet**
and then **Download Wallet**.

![](media/image34.png){width="5.650587270341207in"
height="2.534187445319335in"}

You will be asked to provide a password for the wallet. The password
must meet the rules for the Oracle Cloud password complexity. This
password is a password that you need to remember for your wallet. You
can use the admin password that you created before.

Select **Download** and save the wallet to your local machine.

![](media/image35.png){width="5.106060804899387in"
height="1.879274934383202in"}

You can now **Close** the Database Connection pop up window.

![](media/image36.png){width="6.268055555555556in"
height="2.7840277777777778in"}

#### Use the Wallet in Oracle Analytics Cloud

Return to the Oracle Cloud Infrastructure console and click on the menu
icon on the left.

Navigate to **Analytics** and then **Analytics Cloud**.

![](media/image37.png){width="3.642649825021872in"
height="3.1202537182852144in"}

Open the Cloud Analytics URL associated with your instance (the one that
we created in Lab 200) by using the dots menu button on the right-hand
side of your instance information and selecting **Open URL**.

![](media/image38.png){width="6.254166666666666in"
height="2.0770833333333334in"}

The Oracle Analytics page will open in a new browser window/tab.

On the top right-hand side of the screen, click **Create**, and then
**Connection**.

![](media/image39.png){width="4.451781496062992in"
height="1.987341426071741in"}

Choose **Oracle Autonomous Data Warehouse**.

![](media/image40.png){width="3.3264490376202973in"
height="2.680396981627297in"}

Use the following information to configure your connection.

I recommend selecting first the autonomous database wallet file you just
downloaded (cwallet.sso) in ***Client Credentials*** field so the rest
of the values will be autocompleted. Later on you just have to review
and modify them if need it.

> **Connection Name**: WORKSHOPADWOAC
>
> **Service Name**: Choose the name of your database followed by the
> \_high suffix.
>
> **Client Credentials**: Use the Browse button to upload the wallet zip
> file that you downloaded. It will automatically extract the
> cwallet.sso file from this zip bundle.
>
> **Username**: ADMIN -- We have created this user on the ADW instance
> creation.
>
> **Password**: The password that you created on the ADW instance
> creation at the beginning of the workshop. ADWwelcome-1234

![](media/image41.png){width="4.13628280839895in"
height="4.221519028871391in"}

> Select **Save** to save your new connection information.

### Prepare the dataset

When you create a project, you add one or more data sets containing the
data that you want to visualize and explore. Data sets contain data
from subject areas, Oracle Applications, databases, or uploaded data
files such as spreadsheets. You can also add multiple data sets to your
existing projects.

On the top right-hand side of the *Oracle Analytics* Home Page, click
**Create**, and then **Data Set**.

![](media/image42.png){width="6.263888888888889in"
height="2.4305555555555554in"}

Select **WORKSHOPADWOAC**, the connection you created in the previous
step.

![](media/image43.png){width="3.8958333333333335in"
height="3.282496719160105in"}

In the next window, click on the **SH** (Sales History) schema.

The SH schema provides a small data set you can use to run the sample
queries in the [Oracle Database Data Warehousing
Guide](https://docs.oracle.com/pls/topic/lookup?ctx=en/cloud/paas/autonomous-data-warehouse-cloud/user&id=DWHSG8664).
For more information on the SH schema see *Sample Schemas* and [*Schema
Diagrams*](https://docs.oracle.com/pls/topic/lookup?ctx=en/cloud/paas/autonomous-data-warehouse-cloud/user&id=COMSC112)
in the following
[link](https://docs.oracle.com/pls/topic/lookup?ctx=en/cloud/paas/autonomous-data-warehouse-cloud/user&id=COMSC112).

![](media/image44.png){width="6.268055555555556in"
height="1.8486111111111112in"}

We are ready to start with the visualizations.

![](media/image45.png){width="6.268055555555556in"
height="3.683333333333333in"}

Let start by analysing the Sales History fact table.

Select **SALES** table from the *SH schema*.

![](media/image45.png){width="5.785004374453194in"
height="3.399475065616798in"}

This will display the columns available in the SALES table.

Select **Add All** to select all columns in the table.

![](media/image46.png){width="6.268055555555556in" height="2.16875in"}

After you clicked **Add** to create the Data Set, select **SALES** at
the top of the page (figure 1) or at the right side of the selection
panel (figure 2) depend the version of OAC that you are using to modify
the Data Set that we are currently creating.

Figure 1.

![](media/image47.png){width="6.268055555555556in"
height="2.2743055555555554in"}

Figure 2.

![](media/image48.png){width="6.3in" height="2.2928762029746284in"}

Use the following information to configure your Data Set:

> **Data Access**: Live
>
> **Name**: SH_SALES

Then **Add** to create the Data Set.

![](media/image49.png){width="6.268055555555556in"
height="1.5881944444444445in"}

The Data Set was successfully **added**.

### Create Visualizations using your data sets

Create a new project by clicking **Create Project**.

![](media/image50.png){width="6.268055555555556in"
height="2.379166666666667in"}

A new screen with a white canvas is open using SH_SALES Data Set that we
have created before.

![](media/image51.png){width="6.268055555555556in"
height="3.0101399825021873in"}

Before drowning into details, let us give you a quick explanation of the
different parts of this screen. That will help you to easily follow next
steps.

An Oracle Analytics Project consist of three main parts (you can see
them at the top right part of the screen):

![](media/image52.png){width="1.9045702099737534in"
height="0.3611111111111111in"}

-   **Prepare**: Here is where you configure your data. You get a
    preview of each dataset on the project. You enrich it by adding
    columns, hiding or renaming the available ones. You also define
    joins between datasets here.

-   **Visualize**: Here is where you explore and Analyze the data. You
    can create several canvases to hold the different visualizations you
    define.

```{=html}
<!-- -->
```
-   **Narrate**: Here is where you create a more presentation-oriented
    view of the analysis you created. This tab allows you to choose
    which insights to show and add comments and descriptions. It helps
    to understand your analysis journey and focus on showing the
    results.

During this lab, you will use only **Prepare** and **Visualize** tabs
mainly.

You have already seen the **Prepare** screen on previous steps. The
Visualize screen is this one:

![](media/image51.png){width="6.268055555555556in"
height="3.0097222222222224in"}

Main areas to note here are:

-   **Explorer**: Contains all fields from your datasets to be used in
    the project.

-   **Properties box**: Allows you to define the properties and
    parameters of the selected object. If it is a column it will be
    highlighted in blue (in the screen PROD_ID in the Explorer menu is
    selected) if it is a graphic from the canvas it will have a thin
    blue borderline around it.

-   **Graph Definition**: Contains definition of the selected
    Visualization, which fields to use and where (Axis, Filters, Trellis
    Groups...).

-   **Canvas**: Your play area. You can place your visuals here. You can
    also create more Canvases and copy/move visuals around.

Now that you know a bit your way around in the **Project**, you can
continue with the lab.

Remember that you just added the new dataset from the **SH_SALES**
table.

All the number-type columns from this table are treated as **NUMBER** by
default. You can check the information on the **Properties** section of
each table column under the Data Type section.

![](media/image53.png){width="1.5228029308836395in"
height="3.1260356517935257in"}![](media/image54.png){width="1.5260115923009623in"
height="3.1213877952755906in"}![](media/image55.png){width="1.4508661417322835in"
height="3.1292213473315837in"}![](media/image56.png){width="1.5570417760279964in"
height="3.13041447944007in"}

Select **AMOUNT_SOLD** column from the TABLE panel and add
**Aggregation** rule **SUM** from the COLUMNS detail panel from the
bottom. By default **Aggregation** value, will be **SUM**, just confirm
that it is the case, otherwise change it.

![](media/image57.png){width="1.3699420384951881in"
height="3.768543307086614in"}

We will add Month to your selection: **Hold the Control Button on your
Keyboard** and expand **TIME_ID** and select **Month**, after right
click of your mouse and select **Create Best Visualization**

![](media/image58.png){width="3.2694728783902014in"
height="2.8728324584426947in"}

Verify that the information that is showing in the canvas is the
following:

**Line, Values (Y-Axis) -- AMOUNT_SOLD, Category (X-Axis) -- TIME_ID
(Month).**

![](media/image59.png){width="6.268055555555556in"
height="2.5284722222222222in"}

Right click on the chart, select **Add Statistics** and **Trend Line**.

![](media/image60.png){width="6.2659722222222225in"
height="3.017361111111111in"}

In the **Properties** panel at the very bottom of the page in the
**Trend** section change 95% to **Off**.

![](media/image61.png){width="2.3121391076115487in"
height="4.2022375328083985in"}

![](media/image62.png){width="6.2659722222222225in"
height="2.786111111111111in"}

Although we had some ups and downs in the totals, you see that in the
overall the total amount sold has been trending up, meaning our sales
are in good shape

We will compare this information (AMOUNT_SOLD by TIME_ID (Month)) to our
active customer base over time. To find the number of active customers,
we will "count distinct" on CUST_ID on a Monthly basis.

Select **CUST_ID** column from the TABLE panel and add **Aggregation**
rule **Count Distinct** from the COLUMNS Properties panel from the
bottom.

![](media/image63.png){width="2.1253215223097115in"
height="4.136599956255468in"}

Be sure you drag **CUST_ID** column to the Values (**Y-Axis**) section
with your mouse in the canvas. Be sure it is added AMOUNT_SOLD and not
replace it. Right click on **CUST_ID** and select **Y2 Axis** as part of
the CUST_ID details.

![](media/image64.png){width="0.9782305336832896in"
height="2.8169444444444443in"}

![](media/image65.png){width="6.268055555555556in"
height="2.7715277777777776in"}

This results shows you that the number of customers is going down but
the amount sold is going up, so we are selling more to less customers.

We will create a new Data Set of data to enrich the canvas.

Click the **+** bottom in the left top corner of the Analytics Cloud
Page and **Add Data Set**.

![](media/image66.png){width="4.484373359580053in"
height="2.0870669291338584in"}

Select **Create Data Set**.

![](media/image67.png){width="2.6011559492563427in"
height="0.9504330708661417in"}

Select **WORKSHOPADWOAC**.

![](media/image68.png){width="3.5865048118985126in"
height="1.4400054680664918in"}

Click on the **SH** (Sales History) schema.

![](media/image44.png){width="6.268055555555556in"
height="1.8486111111111112in"}

Select **PRODUCTS** table from the *SH schema*.

![](media/image45.png){width="6.268055555555556in"
height="3.683333333333333in"}

This will display the columns available in the **PRODUCTS** table.

Select **Add All** to select all columns in the table.

![](media/image69.png){width="6.268055555555556in"
height="2.0791666666666666in"}

Then, to create the Data Set, select **PRODUCTS** at the top of the page
or at the right side of the selection panel depend the version of OAC
that you are using to modify the Data Set that we are creating right
now.

![](media/image69.png){width="6.268055555555556in"
height="2.0791666666666666in"}

Use the following information to configure your Data Set:

> **Data Access**: Live
>
> **Name**: SH_PRODUCTS

Then **Add** to create the Data Set.

![](media/image70.png){width="6.268055555555556in"
height="1.3291666666666666in"}

The Data Set was successfully **saved**.

![](media/image71.png){width="6.268055555555556in"
height="1.8770833333333334in"}

Now we have to join the new Data Set, SH_PRODUCT, to the data set that
we created a few steps before SH_SALES.

You can notice that we have been redirected to the **Prepare** section
of the project.

At the bottom of the screen, you can see three tabs, one per each
dataset and another one called **Data Diagram**. Click on it.

![](media/image72.png){width="6.268055555555556in"
height="2.8805555555555555in"}

In this tab, you can view a representation of the different datasets
included in the project and their relationships. Currently, there is no
relation defined, so you see both as isolated boxes.

Hover over the imaginary line between them and click on the 0 number
that will appear:

![](media/image73.png){width="3.557292213473316in"
height="1.4374114173228347in"}

A pop-up window appears allowing you to define a new relation between
the datasets (join). Click on **Add Another Match**.

![](media/image74.png){width="3.4444444444444446in"
height="2.6610017497812772in"}

Select **PROD_ID** under each Data Set, SH_PRODUCTS and SH_SALES in the
**Select Data** Section.

![](media/image76.png){width="3.1860083114610673in"
height="2.826388888888889in"}

![](media/image77.png){width="3.2222222222222223in"
height="2.8527252843394577in"}

**NOTE**: You might see a balloon warning about using **PROD_ID** as a
**Measure**. Do not worry about it. It is just a kind reminder that you
are using a column that looks like a number only as a join column, but
that is exactly what we want to do.

![](media/image78.png){width="1.8385422134733158in"
height="0.38781714785651794in"}

We will add the new dataset as a Dimension to this section. Click **Add
Facts** and select **Extend a Dimension**.

![](media/image79.png){width="2.8819444444444446in"
height="1.8958333333333333in"}

Select **OK**.

![](media/image80.png){width="3.10910542432196in"
height="2.2360433070866144in"}

The connection between the two sources has been created.

![](media/image81.png){width="6.268055555555556in"
height="1.9527777777777777in"}

Now that the preparation of the data is done, you can navigate again to
**Visualize** page in the right top corner of the Analytics Cloud Home
Page.

![](media/image52.png){width="1.9045702099737534in"
height="0.3611111111111111in"}

In the canvas go to **TIME_ID** section, **Show by** and select
**Quarter** instead Month.

![](media/image82.png){width="6.263888888888889in"
height="3.2291666666666665in"}

Apply the **Quarter** filter and the graph will change dynamically.

![](media/image83.png){width="6.268055555555556in"
height="3.1847222222222222in"}

We will eliminate the Linear Trend Line that we have in the graph.

Click in the graph and in the Properties section of the bottom of the
page, select the **Analytics** icon and click in the **Trend** section
to remove the **Linear** section.

![](media/image84.png){width="6.268055555555556in"
height="2.879166666666667in"}

We can see the graph without the Trend Linear line.

![](media/image85.png){width="6.268055555555556in"
height="3.1729166666666666in"}

Select **PRODUCT_CATEGORY** from **SH_PRODUCTS** and add it in **the
Trellis Columns** section of the canvas.

![](media/image86.png){width="2.696548556430446in"
height="3.8077121609798774in"}

![](media/image87.png){width="6.268055555555556in"
height="3.0743055555555556in"}

You can see now a trend on the amount sold and number of distinct
customers by product category and that allows comparing the performance
of each product. However, using just lines can be a bit messy. You will
try now to make this graphic more appealing.

Select **AMOUNT_SOLD** from the canvas and select **Bar** graph.

![](media/image88.png){width="1.6180555555555556in"
height="3.7735575240594925in"}

Select **Project Properties** from the Burger Menu in the right top
corner.

![](media/image89.png){width="6.268055555555556in"
height="2.888888888888889in"}
![](media/image90.png){width="1.7361111111111112in"
height="2.036130796150481in"}

Select in the **Colour Series** and select another colour that you
prefer.

![](media/image91.png){width="2.6229527559055117in"
height="4.266748687664042in"}

Select **OK** after being applied the colour changes.

![](media/image92.png){width="6.302168635170604in"
height="2.6944444444444446in"}

![](media/image93.png){width="6.268055555555556in"
height="3.152083333333333in"}

We will save the Project in the **Save** section.

![](media/image94.png){width="3.1458333333333335in"
height="1.39372375328084in"}

I saved the project with the name **ADW_OAC_SH_SCHEMA**.

![](media/image95.png){width="6.268055555555556in"
height="2.717361111111111in"}

You can share your project by email or social media. Have a look at the
possibilities.

Select the Share icon and select File or Print.

![](media/image96.png){width="2.6875in" height="1.5651804461942258in"}

You can choose to **Save** your project in a wide variety of standard
formats such as PowerPoint (pptx), Acrobat (pdf), Image (png), Data
(csv), Package (dva).  You can choose which parts of your project to
include, such as All Canvas, only the Active Canvas or the Active
Visual.

![](media/image97.png){width="2.0833333333333335in"
height="2.1641786964129484in"}

![](media/image98.png){width="2.0416666666666665in"
height="2.190149825021872in"}

The file will be downloaded locally on your machine.

![](media/image99.png){width="2.8881944444444443in"
height="2.642361111111111in"}

When you select **Print**, you can choose which parts of your project to
include in the printed output, such as All Canvas, only the Active
Canvas or the Active Visual. Etc.

![](media/image100.png){width="6.268055555555556in"
height="3.3472222222222223in"}

Appendix A - Provisioning an Oracle Analytics Cloud Instance {#appendix-a---provisioning-an-oracle-analytics-cloud-instance .list-paragraph}
============================================================

If your Oracle Cloud account started before 14 February 2020 (USA) or
2nd March 2020 (EMEA), you have the option to deploy Oracle Analytics
Cloud Instances using a different method. This is documented below for
completeness, but it is expected that people running the workshop to use
the Oracle Analytics Cloud on Oracle Cloud Infrastructure Gen 2, which
is documented in the main body of the document.

Your Oracle Cloud Free Tier account will use the Oracle Cloud Free Trial
credits while this instance is provisioned, as Oracle Analytics Cloud is
not part of the Always Free cloud services.

Provisioning an Oracle Analytics Cloud instance can take over 40
minutes. If you plan to run Lab 300 during the classroom session, then
you can provision the instance now and have it ready for use later.

Return to the Oracle Cloud Infrastructure console, click on the menu
icon on the left. Verify that you are signed in as a Single Sign On
(idcs) user by selecting the **Profile** icon in the top right hand side
of your screen. If your username is shown as:

oracleidentitycloudservice / \<your username\>

Then you are connected as a Single Sign On user.

![](media/image25.png){width="5.041666666666667in"
height="3.1770833333333335in"}

If your username is shown as:

\<your username\>

Then you are not signed in as an Oracle Cloud Infrastructure user.

![](media/image26.png){width="4.6875in" height="3.2291666666666665in"}

If your user does not contain the identity provider --
(oracleidentitycloudprovider), please logout and select to authenticate
using Single Sign On.

![](media/image27.png){width="6.268055555555556in"
height="3.4402777777777778in"}

To be capable of using Oracle Analytics Cloud we need to be Sign-On as a
Single Sign-On (SSO) user.

More information about federated users:
<https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/usingscim.htm>

Return to the *Home Console Page* and navigate to **Platform Services**
under **More Oracle Cloud Services** section and then **Analytics**.

![](media/image101.png){width="3.4930555555555554in" height="5.8125in"}

***Note**: You must be connected as a Single Sign On (idcs) user to a
tenancy, which has available cloud credits to see this menu item. Local
OCI users are not able to do this.*

This will open a new browser tab/window. Select **Create Instance**.

![](media/image102.png){width="6.268055555555556in"
height="2.2868055555555555in"}

Complete the form using the following information:

**Instance Name**: WORKSHOPADWOAC

**Region**: No preference

> **License Type**: \"Subscribe to a new Analytics Cloud software
> license and the Analytics Cloud.\" (You will use this service as part
> of the free Oracle Cloud trial that you requested for this workshop)

**Edition**: Oracle Analytics Cloud - Professional (important)

**Feature Set**: Professional Edition Feature Set (important)

**Number of OCPUs**: 1 - Non Production

Select **Next**.

![](media/image103.png){width="6.268055555555556in"
height="3.7895833333333333in"}

On the Confirmation screen, select **Create**.

![](media/image104.png){width="6.268055555555556in"
height="2.0527777777777776in"}

The Analytics instance page will be displayed with a status of *CREATING
service*.

![](media/image105.png){width="6.268055555555556in"
height="2.754861111111111in"}

The Analytics instance page will be displayed the OAC instance created
and the status is *Ready*.

![](media/image106.png){width="5.415384951881014in"
height="2.438902012248469in"}

![](media/image107.png){width="5.374097769028872in"
height="2.080929571303587in"}

You can now proceed onto running the labs.

Want to learn more about ADW & OAC? {#want-to-learn-more-about-adw-oac .list-paragraph}
===================================

Oracle Autonomous Data Warehouse offitial Documentation:

<https://docs.oracle.com/en/cloud/paas/autonomous-data-warehouse-cloud/>

Oracle Autonomous Data Warehouse on Shared Exadata Infrastructure:

> <https://docs.oracle.com/en/cloud/paas/autonomous-data-warehouse-cloud/user/autonomous-intro-adw.html#GUID-4B91499D-7C2B-46D9-8E4D-A6ABF2093414>

Oracle Analytics Cloud offitial Documentation:

<https://docs.oracle.com/en/cloud/paas/analytics-cloud/index.html>

Oracle Analytics Cloud - What Is Oracle Analytics Cloud Documentation:

<https://www.oracle.com/business-analytics/analytics-cloud.html>

+----------------------------------+----------------------------------+
| ![](media/image108.p             | Oracle Corporation, World        |
| ng){width="1.0770833333333334in" | Headquarters Worldwide Inquiries |
| height="0.3368055555555556in"}   |                                  |
|                                  | 500 Oracle Parkway Phone:        |
|                                  | +1.650.506.7000                  |
|                                  |                                  |
|                                  | Redwood Shores, CA 94065, USA    |
|                                  | Fax: +1.650.506.7200             |
+==================================+==================================+
| ![](media/image109.p             | > Copyright © 2020, Oracle       |
| ng){width="1.9708333333333334in" | > and/or its affiliates. All     |
| height="1.5819444444444444in"}   | > rights reserved. This document |
|                                  | > is provided *for* information  |
|                                  | > purposes only, and the         |
|                                  | > contents hereof are subject to |
|                                  | > change without notice. This    |
|                                  | > document is not warranted to   |
|                                  | > be error-free, nor subject to  |
|                                  | > any other warranties or        |
|                                  | > conditions, whether expressed  |
|                                  | > orally or implied in law,      |
|                                  | > including implied warranties   |
|                                  | > and conditions of              |
|                                  | > merchantability or fitness for |
|                                  | > a particular purpose. We       |
|                                  | > specifically disclaim any      |
|                                  | > liability with respect to this |
|                                  | > document, and no contractual   |
|                                  | > obligations are formed either  |
|                                  | > directly or indirectly by this |
|                                  | > document. This document may    |
|                                  | > not be reproduced or           |
|                                  | > transmitted in any form or by  |
|                                  | > any means, electronic or       |
|                                  | > mechanical, for any purpose,   |
|                                  | > without our prior written      |
|                                  | > permission.                    |
|                                  | >                                |
|                                  | > Oracle and Java are registered |
|                                  | > trademarks of Oracle and/or    |
|                                  | > its affiliates. Other names    |
|                                  | > may be trademarks of their     |
|                                  | > respective owners.             |
|                                  | >                                |
|                                  | > Intel and Intel Xeon are       |
|                                  | > trademarks or registered       |
|                                  | > trademarks of Intel            |
|                                  | > Corporation. All SPARC         |
|                                  | > trademarks are used under      |
|                                  | > license and are trademarks or  |
|                                  | > registered trademarks of SPARC |
|                                  | > International, Inc. AMD,       |
|                                  | > Opteron, the AMD logo, and the |
|                                  | > AMD Opteron logo are           |
|                                  | > trademarks registered          |
|                                  | > trademarks of Advanced Micro   |
|                                  | > Devices. UNIX is a registered  |
|                                  | > trademark of The Open Group.   |
+----------------------------------+----------------------------------+
