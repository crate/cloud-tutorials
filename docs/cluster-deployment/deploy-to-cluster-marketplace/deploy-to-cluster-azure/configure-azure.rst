.. _configure-azure-to-cluster:

=================================
Configure and deploy your cluster
=================================

After having subscribed to the Microsoft Azure Marketplace offer, you can now
start to deploy your first cluster by going through the CrateDB Cloud Console
configuration wizard. Here we will walk you through the process.


.. rubric:: Table of contents

.. contents::
   :local:


.. _configure-azure-to-cluster-config:

Configuration
=============

To recap from the previous tutorial: to deploy your cluster, first it must be
configured. If you have not yet done so, go to the Azure Portal's *Home >
(SaaS)* page. Inside it, select the subscription you created. Now click on
*Configure Account* on the overview menu.

.. image:: ../../../_assets/img/azure-config-account.png
   :alt: Azure SaaS configuration screen

You will now be redirected to the CrateDB Cloud Console.

Once in the Console, if necessary, authenticate with the Microsoft Azure
account you used to create the offer in the previous step.

.. WARNING::

    It is important that you use the Microsoft login option rather than any
    other, otherwise you will not be able to deploy a cluster with the correct
    subscription plan.

Now complete the three-step wizard to deploy the cluster.


.. _configure-azure-to-cluster-wizard:

Wizard
======

Wizard step 1
-------------

In this step, you must first define an organization, if you have not already
done so. (If you have, it will be pre-selected for you.) You must also select a
region for your project (within which the cluster will be deployed), and either
name a new project or choose an existing one if you have one.

.. image:: ../../../_assets/img/azure-wizard-step1.png
   :alt: CrateDB Cloud configuration wizard step 1

You may also notice a popup in the right bottom corner. This is to welcome you
after your signup to CrateDB Cloud. In it, you will find a link to our `help
document on cluster deployment`_, which provides a quick summary of the same
process described in this tutorial. If you want, you can also reply to it. This
puts you in contact with the Crate.io team.

Fill out the required lines and click *Next* to continue.


Wizard step 2
-------------

In the second step of the CrateDB Cloud Console configuration wizard, you can
define your cluster name. You must also set the username and password used to
directly access the cluster via its URL. The password must be at least 24
characters long; any characters are accepted, including special characters. If
you want, click the *Auto-generate password* button to automatically generate
a secure 24 character password.

.. image:: ../../../_assets/img/azure-wizard-step2.png
   :alt: CrateDB Cloud configuration wizard step 2

Finally, you can also set the scale unit of the cluster to the desired level
here. As you move the slider horizontally, you will move up (or down) the scale
levels within the subscription plan you previously selected. As you will see,
the hardware capacities of the cluster will change correspondingly. Currently,
within each subscription plan clusters can be scaled between scale units 1-3.
The default scale unit is 1. Note that scaling the cluster changes its price.

Do not worry, however: clusters can be scaled up or down as needed - for
example if your use case changes - at any point later on. To understand more
about subscription plans, scaling, and scale units, refer to our `reference on
subscription plans`_ and our `scaling guide`_.

When you have filled out the required lines and chosen a scale unit, click
*Next* to proceed.


Wizard step 3
-------------

The final step of the configuration wizard provides you with a summary of your
previous choices and the overall result. First, it shows the settings for your
organization and project, with the names you have defined. Next, it shows
the cluster information, including the version of CrateDB the cluster will be
running and once again the scale unit capacities the cluster will have.
Finally, the pricing information shows you the relevant costs of running the
cluster. Note that Crate.io always bills for usage on an hourly basis, and only
actual usage is ever billed. (You can at any time check your current
accumulated bill at the bottom left of the CrateDB Cloud Console screen.)

.. image:: ../../../_assets/img/azure-wizard-step3.png
   :alt: CrateDB Cloud configuration wizard step 3

Take a moment to review. If you are satisfied, click *Deploy*, and the cluster
will be deployed. Eventually, you will be forwarded to the `CrateDB Cloud
Console`_.


.. _configure-azure-to-cluster-connect:

Deploy and connect
==================

A popup menu will remind you of the username and password you selected for
connecting to the cluster. Make sure you copy this information to a safe place
(e.g., a password manager), as it will not be retrievable past this point.

The new cluster should be visible inside the project where you created it in
the left hand menu. Please keep in mind that the deployment can take some time
depending on the size of the cluster. Usually it takes about 10 to 20 minutes.

To test if your cluster is available, go to *Cluster Overview* in the Console
and click on the cluster URL. Once the cluster is up and running you should be
presented with a login form. Enter the database user and password defined in
step 2 of the wizard. After authentication the CrateDB Admin UI opens and you
can start using your cluster. For more information, visit `our Admin UI
documentation`_.


.. _CrateDB Cloud Console: https://crate.io/docs/cloud/reference/en/latest/overview.html
.. _help document on cluster deployment: http://help.crate.io/en/articles/3967131-how-do-i-deploy-a-cluster-via-the-azure-marketplace
.. _our Admin UI documentation: https://crate.io/docs/crate/admin-ui/en/latest/console.html
.. _reference on subscription plans: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html
.. _scaling guide: https://crate.io/docs/cloud/howtos/en/latest/scale-cluster.html