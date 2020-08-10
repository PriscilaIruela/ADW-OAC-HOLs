# Lab 300 - Using Oracle Analytics Cloud (OAC)

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

## Create the connection from Oracle Analytics Cloud to Autonomous Database

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

### Download your Autonomous Database wallet

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

### Use the Wallet in Oracle Analytics Cloud

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

## Prepare the dataset

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

## Create Visualizations using your data sets

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