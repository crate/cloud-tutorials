.. _configure-aws-to-cluster:

=================================
Configure and deploy your cluster
=================================

After having subscribed to the AWS Marketplace offer, you can now start to
use your first cluster. This involves two steps: the deployment of the cluster
in the CrateDB Cloud Console, and the configuration of the cluster (including
choosing the subscription plan) by going through the CrateDB Cloud Console
wizard. Here you will find a step-by-step description of the process.

.. rubric:: Table of contents

.. contents::
   :local:


.. _configure-aws-to-cluster-deploy:

Deploy your cluster
===================

After having subscribed, you should arrive (possibly involving a subsequent
login process) at the CrateDB Cloud Console. The Console will display the
subscriptions tab of the Organization overview page, where you can see any and
all subscriptions that your organization has.

.. image:: ../../../_assets/img/aws-subscription-overview.png
  :alt: CrateDB Cloud Console organization overview page

Under the relevant subscription, click the *Deploy cluster* button. This will
take you to the CrateDB Cloud configuration wizard, starting with the choice
of subscription plan.


.. _configure-aws-to-cluster-plans:

Choose a plan
=============

You choose a subscription plan at this stage of configuration. CrateDB Cloud
currently offers four different standard subscription plans: *Development*,
intended for trying out the service, *General Purpose*, designed to meet
production-ready use cases, *IO Optimized* for use cases where query speed is
the main focus, and *Storage Optimized* for cases where large amounts of (hot)
storage are essential. Finally, there is the `CrateDB Cloud Contract`_,
offering an annual subscription to our cloud service by paying in advance. To
learn more about our subscription plans, see the `reference on subscription
plans`_.

.. image:: ../../../_assets/img/aws-config-plans.png
   :alt: CrateDB Cloud plans

Choose the plan of your liking by clicking the relevant *Choose* button and
proceed.


.. _configure-aws-to-cluster-wizard:

Wizard
======

You will now enter the CrateDB Cloud Console configuration wizard, where the
final steps for cluster configuration and deployment await.


Wizard step 1
-------------

After having chosen the desired subscription plan, you are referred to the
first stage of the wizard that will configure and deploy your cluster. In this
step, you must first define an organization, if you have not already done so.
(If you have, it will be pre-selected for you.) You must also select a region
for your project (within which the cluster will be deployed), and either name
a new project or choose an existing one if you have one.

.. image:: ../../../_assets/img/aws-wizard-step1.png
   :alt: CrateDB Cloud configuration wizard step 1

You may also notice a popup in the right bottom corner. This is to welcome you
after your signup for CrateDB Cloud. In it, you will find a link to our help
document on cluster deployment, which provides a quick summary of the same
process described in this tutorial. If you want, you can also respond. This
gets you in contact with the Crate.io team.

Fill out the required lines and click *Next* to continue.


Wizard step 2
-------------

In the second step of the CrateDB Cloud Console configuration wizard, you can
define your cluster name. You must also set the username and password used to
directly access the cluster via its URL. The password must be at least 24
characters long; any characters are accepted, including special characters. If
you want, click the *Auto-generate password* button to automatically generate
a secure 24 character password.

.. image:: ../../../_assets/img/aws-wizard-step2.png
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
actual usage is ever billed.

.. image:: ../../../_assets/img/aws-wizard-step3.png
   :alt: CrateDB Cloud configuration wizard step 3

Take a moment to review. If you are satisfied, click *Deploy*, and the cluster
will be deployed. Eventually, you will be forwarded to the `CrateDB Cloud
Console`_.


Deploy and connect
==================

A popup menu will remind you of the username and password you selected for
connecting to the cluster. Make sure you copy this information to a safe place
(e.g., a password manager), as it will not be retrievable past this point.

The new cluster should be visible inside the project where you created it in
the left hand menu. Please keep in mind that the deployment can take some time
depending on the size of the cluster.

To test if your cluster is available, go to *Cluster Overview* in the Console
and click on the cluster URL. Once the cluster is up and running you should be
presented with a login form. Enter the database user and password defined in
step 2 of the wizard. After authentication the CrateDB Admin UI opens and you
can start using your cluster. For more information on accessing the Admin UI,
visit `our Admin UI documentation`_.


.. _CrateDB Cloud  Console: https://crate.io/docs/cloud/reference/en/latest/overview.html
.. _CrateDB Cloud Contract: https://aws.amazon.com/marketplace/pp/B08KHK34RK
.. _our Admin UI documentation: https://crate.io/docs/crate/admin-ui/en/latest/console.html
.. _reference on subscription plans: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html
.. _scaling guide: https://crate.io/docs/cloud/howtos/en/latest/scale-cluster.html