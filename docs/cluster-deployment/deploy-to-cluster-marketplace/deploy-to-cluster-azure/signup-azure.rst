.. _signup-azure-to-cluster:

====================================================
Subscribe to CrateDB Cloud via the Azure Marketplace
====================================================

One way to deploy a CrateDB cluster on CrateDB Cloud is via the Microsoft Azure
Marketplace. You will need a Microsoft Azure account and an Azure subscription
with a credit card linked to it. By using CrateDB Cloud's service on Azure
Marketplace, your hourly usage is billed directly by Microsoft, not by
Crate.io.

As a SaaS service, the subscription payment is arranged through Azure. The
cluster will be hosted in the region you select as part of the configuration
process. If you are looking for a self-hosted CrateDB Cloud service, check out
the :ref:`CrateDB Edge tutorial <edge>`. To pay directly for a hosted cluster
by credit card, see our tutorial for :ref:`direct cluster deployment
<cluster-deployment-stripe>`.

.. rubric:: Table of contents

.. contents::
   :local:


.. _signup-azure-to-cluster-offer:

Using the CrateDB Cloud offer on Azure Marketplace
==================================================

Visit the CrateDB Cloud offer on the `Azure Marketplace`_. Under the *Plans +
Pricing* tab you will find useful information on available cluster
configurations. The Development plan is suitable as a demo of CrateDB Cloud.
For production ready use cases, there is a General Purpose plan, as well as
I/O Optimized and Storage Optimized plans. Finally, there is the CrateDB Cloud
Contract for paying yearly in advance on the basis of direct negotiation with
our Sales team. For details on these plans, see our `documentation on
subscription plans`_.

.. image:: ../../../_assets/img/azure-plans.png
   :alt: Azure Marketplace CrateDB Cloud plans

Once you know which plan suits your needs, click the blue *Get It Now* button
to the left to take up the CrateDB Cloud offer. After giving consent to
Microsoft sharing basic account information (you may be required to log in with
Azure), you will be redirected to the Azure Portal page for the CrateDB Cloud
offer. This page provides a dropdown menu where you can now select the plan you
have identified previously.

.. image:: ../../../_assets/img/azure-portal-offer.png
   :alt: Azure Portal CrateDB Cloud offer

Simply select your preferred plan and confirm by clicking *Set up + Subscribe*.
Note that you can still review the plans and pricing again at this stage before
creating a subscription.

The next page allows you to configure the subscription you have just chosen.
First, name your subscription. Then choose a subscription type that should be
billed for the total usage. All resources in a single Azure subscription are
billed together. You can also define a resource group and its location here. A
resource group is a set of resources with the same life cycle, permissions, and
policies. For more information on these, refer to the `Azure documentation on
resource groups`_. Optionally, you can also set tags for this resource. More
information about tags can be found in the `Azure documentation on tags`_.

.. image:: ../../../_assets/img/azure-subscribe-offer.png
   :alt: CrateDB Cloud on Azure subscription

Once everything is set, click *Review + Subscribe* in the bottom left corner
and accept the terms of use by clicking *Subscribe* again.

Your offer with the desired subscription is now being created. This might
take a few seconds. You'll see the result in the Azure Portal's *Notifications*
menu. Once the offer has been created you can access it either by clicking on
the notification *Configure account now* when it appears.

Alternatively, go to *Home > Software as a Service (SaaS)* and select the
service you just created from the listing of subscriptions. (You may have to
navigate via *SaaS (Classic)*, depending on whether you had Azure resources
before Microsoft Azure changed their interface.) Possibly you will see an
orange warning sign in the overview. This is because you first have to
configure and deploy your cluster on CrateDB Cloud. Until this is done, the
cluster will not be active and nothing will be billed.

In either case, you will be referred to the CrateDB Cloud Console for further
configuration.


.. _signup-azure-to-cluster-next:

Next steps
==========

The next steps are to configure your cluster in the CrateDB Cloud Console
wizard and, finally, to deploy your cluster. This will be explained in the
:ref:`next section of the tutorial <configure-azure-to-cluster>`.


.. _Azure documentation on resource groups: https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal
.. _Azure documentation on tags: https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources
.. _Azure Marketplace: https://azuremarketplace.microsoft.com/en-us/marketplace/apps/crate.cratedbcloud?tab=Overview
.. _documentation on subscription plans: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html