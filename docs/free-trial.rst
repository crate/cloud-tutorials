.. _free-trial:

==========
Free trial
==========

If you want to try out CrateDB Cloud's potential, there are multiple ways to do
this. One is to subscribe to one of the CrateDB Cloud offers via our SaaS
marketplace offers and to choose the `Development subscription plan`_. For a
full guide on how to subscribe via the marketplace offers, see our
:ref:`tutorials on deploying a cluster from scratch <sign-up>` above.

The other is to avail yourself of the possibility of our free trial: a fully
functioning CrateDB Cloud cluster running for 14 days without cost, so you can
experience the benefits of CrateDB Cloud without any immediate commitment.

In this guide, we describe step by step how to activate the CrateDB Cloud free
trial offer. The CrateDB Cloud structure is based on organizations, and within
these organizations run projects that contain the deployed clusters. To deploy
your free trial cluster, you therefore need an organization and a project to
deploy it in as well. Fortunately, these are created quite easily as part of
the deployment process, as will be shown in the following steps.


.. _free-trial-signup:

Sign up
=======

In order to access CrateDB Cloud, you must first sign up with an account.
Simply follow the steps in the :ref:`tutorial for signing up <sign-up>`. When
you have successfully signed up, you will be forwarded to the CrateDB Cloud
Console subscription overview. It is from here that you can make use of the
free trial option. The first step is to set up an organization.


.. _free-trial-org:

Create an organization
======================

Before the free trial can be deployed, it is necessary to create an
organization within the CrateDB Cloud Console. The trial cluster is then
deployed within this organization. When you arrive for the first time at the
Console subscription overview, you should be prompted to create an
organization.

.. image:: _assets/img/free-trial-organization.png
   :alt: Create an organization

Enter the desired name for the organization in the field and click *Create
organization*. Once you have done so, you will see in the subscription overview
screen a set of options for choosing a cloud provider: Microsoft Azure or
Amazon AWS. Below them is the free trial cluster option.

.. image:: _assets/img/free-trial-link.png
   :alt: Free trial cluster

You can now deploy the free trial cluster by clicking the *Launch free 14-day
trial cluster* button. This will take you to the configuration wizard for the
cluster, which will complete the process.


.. _free-trial-configure:

Configure the free cluster
==========================

In the configuration wizard, the organization you have created will be
pre-selected. All that remains is to choose a region where the cluster will be
deployed and to name the project your free trial cluster will be a part of.
When you are done, click *Next*.

.. image:: _assets/img/free-trial-project.png
   :alt: Name a project

The next step requires you to name the cluster itself and to configure a
username and password to access the cluster directly through the CrateDB Cloud
admin UI. (Note that this username and password are distinct from the one used
to access the CrateDB Cloud Console.)

.. image:: _assets/img/free-trial-clusterconfig.png
   :alt: Configure the cluster

When this is complete, click *Next* again. This will show you a summary of the
cluster configuration and the subscription tier (free trial) you are deploying.
It also shows you the storage, query, and ingest capacity of the cluster. The
price, of course, is $0.

.. image:: _assets/img/free-trial-summary.png
   :alt: Cluster summary

If you are happy with the results, click *Deploy*. Your free trial cluster will
now be deployed and you will be returned to the CrateDB Cloud Console.


.. _free-trial-expiry:

Free trial expiry
=================

After 14 days, the free trial cluster will automatically expire and no longer
be accessible. You do not have to do anything to cancel or remove it. To
continue using the CrateDB Cloud service after the 14 days, you can
:ref:`subscribe to one of our marketplace offers <cluster-deployment>`.


.. _Development subscription plan: https://crate.io/docs/cloud/reference/en/latest/subscription-plans.html