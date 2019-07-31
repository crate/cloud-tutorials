.. highlights:: console

=====================================
Create first Organization and Project
=====================================

During the preceding chapters of this CrateDB Cloud getting started guide, you
have created your `CrateDB Cloud user account`_ and `accessed CrateDB Cloud`_.

Create your first organization
==============================

In this section you will learn how to create your first organization.

Run the following command:

.. code-block:: console

    sh$ croud organizations create --name CrateOrganization --plan-type 1

Parameters
^^^^^^^^^^

* With the --name parameter you can specify the name of your organization
* The --plan-type parameter indicates the support plan you want to use

This example uses support plan 1, which provides regular business hours support

If you have run the command and the Croud CLI returns the an organization id,
then you hace successfully created your firstorganization.

You’ve also automatically become a member to your organization.

Validate organization membership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You can validate your organization membership by running the following command
in the Croud CLI:

.. code-block:: console

    sh$ croud organizations list

The Croud CLI shold now display a list of all organizations your user is a
member of.

You have learned how to create create our first organization.  and deploy a CrateDB database as well as an EventHub consumer to ingest data.

Create your first project
=========================


Next steps
==========

`Deploy CrateDB cluster`_.

.. _Deploy CrateDB cluster: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/deploy_first_cluster.html
.. _Create your first CrateDB Cloud user account: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/create_account.html
.. _accessed CrateDB Cloud_: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/accessing_cdb_cloud.html
