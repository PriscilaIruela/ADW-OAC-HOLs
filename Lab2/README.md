# Lab 200 - Provisioning your Oracle Analytics Cloud (OAC) instance

There are currently two methods of deploying **OAC instances**. This section describes the process of deploying **Oracle Analytics Cloud** instances on Oracle Cloud Infrastructure Gen 2, which is the default for newly provisioned accounts in EMEA and US.

Your Oracle Cloud Free Tier account will use the Oracle Cloud Free Trial credits while this instance is provisioned, as Oracle Analytics Cloud is
not part of the Always Free cloud services.

Provisioning an Oracle Analytics Cloud instance can take over **40 minutes**.

Return to the Oracle Cloud Infrastructure Console accessing from **Oracle Home Page** (oracle.com) and sign in into your cloud account.
Click in **View Account** and **Sign in to Cloud**.

![Oracle Console SignIn](/images/lab200_1.png)

Click on the menu icon on the left. Verify that you are signed in as a Single Sign On (Federated user) user by selecting the **Profile** icon
in the top right hand side of your screen. If your username is shown as:

> oracleidentitycloudservice / \<your username\>
>
Then you are connected as a Single Sign On user.

![](media/image25.png){width="5.041666666666667in"
height="3.1770833333333335in"}

If your username is shown as:

>\<your username\>
>
Then you are not signed in as an Oracle Cloud Infrastructure user.

![](media/image26.png){width="4.6875in" height="3.2291666666666665in"}

If your user does not contain the identity provider --(oracleidentitycloudprovider), please logout and select to authenticate
using Single Sign On.

![](media/image27.png){width="6.268055555555556in"
height="3.4402777777777778in"}

To be capable of using Oracle Analytics Cloud we need to be Sign-On as a Single Sign-On (SSO) user.

[More information about federated users.](https://docs.cloud.oracle.com/en-us/iaas/Content/Identity/Tasks/usingscim.htm)

Return to the *Home Console Page* and navigate to **Analytics** under **Solutions and Platform** section and then **Analytics Cloud**.

![](media/image28.png){width="4.138194444444444in"
height="3.015277777777778in"}

***Note**: You must be connected as a Single Sign On (Federated user) user to a tenancy, which has available cloud credits to see this menu
item. Local OCI users are not able to do this.*

Select **Create Instance**.

Complete the form using the following information:

> **Compartment**: Select a valid compartment in your tenancy.
>
>**Instance Name**: WORKSHOPADWOAC
>
>**Description**: \<optional\>
>
>**Feature Set**: Enterprise Analytics (important)
>
>**Capacity**: 1 - Non Production
>
> **License Type**: \"Subscribe to a new Analytics Cloud software > license and the Analytics Cloud.\" (You will use this service as part
> of the free Oracle Cloud trial that you requested for this workshop).

Select **Create**.

![](media/image29.png){width="6.268055555555556in" height="3.23125in"}

On the Confirmation screen, select **Create**.

The Analytics instance page will be displayed with a status of *CREATING*.

![](media/image30.png){width="6.268055555555556in"
height="3.6756944444444444in"}

***Reminder***: Provisioning an Oracle Analytics Cloud instance can take over 40 minutes.

The Analytics instance page will be displayed with a status of *ACTIVE*.

![](media/image31.png){width="6.268055555555556in" height="3.41875in"}

You can now proceed onto running the labs.

## Congratulations, you are ready for the next Lab!

---

[**<<<<< Go to Lab 1**](../Lab1/README.md) | [Home](../README.md) | [**Go to Lab 3 >>>>>**](../Lab3/README.md)