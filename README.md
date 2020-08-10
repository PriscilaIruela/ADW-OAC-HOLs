
# Oracle Autonomous Data Warehouse and Oracle Analytics Cloud Hands on Lab Guide

[Lab Introduction]

[Lab technical requirement]


## Table of Contents

[Lab 000 - Creating and connecting to your Oracle Cloud Free Tier Account](./Lab0/README.md=)

[Lab 100 - Provisioning your Autonomous Database instance](./Lab1/README.md=)

[Lab 200 - Provisioning your Oracle Analytics Cloud (OAC) instance](./Lab2/README.md=)

[Lab 300 - Using Oracle Analytics Cloud (OAC)](./Lab3/README.md=)

[Appendix] (./Appendix/README.md=)
 - [Want to learn more about ADW & OAC?]

## Lab Introduction

In this hands-on lab, you will get first-hand experience of using Oracle Cloud, Oracle Autonomous Database (ADB) and Oracle Analytics Cloud (OAC).

Oracle Autonomous Database (ADB) delivers a self-driving, self-securing,self-repairing database service that can instantly scale to meet demands. The service supports two workload types:

-   **Oracle Autonomous Data Warehouse (ADW)** provides an autonomous warehousing environment, associated with fast query performance.

-   **Oracle Autonomous Transaction Processing (ATP)** provides an autonomous online transaction processing and mixed workload environment.

For the purpose of this lab, we will use ADW so all the steps will be related to this database service.

**Oracle Analytics Cloud (OAC)** is a scalable and secure public cloud service that provides a full set of capabilities to explore and perform collaborative analytics for you, your workgroup, and your enterprise.

With Oracle Analytics Cloud, you also get flexible service management capabilities, including fast setup, easy scaling and patching, and automated lifecycle management.

To run the lab, you will need an Oracle Free Tier Account, with a provisioned ADW instance and a a provisioned OAC instance. This pre-requisite guide will take you step-by-step through how to get the account and set the instance up, to be ready to start the lab.

### Lab Requirement

As you will be registering for services in Oracle Cloud, you will also need:

-   Access to the email account used to register for the workshop.

-   A cell phone to receive an SMS for account verification processes.









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

