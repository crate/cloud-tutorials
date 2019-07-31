.. highlights:: console

=====================================
Create first Organization and Project
=====================================

During the preceding chapters of this CrateDB Cloud getting started guide, you
have created your `CrateDB Cloud user account`_ and `accessed CrateDB Cloud`_.

Create your first organization
==============================

In this section you will learn how to create your first organization. In
CrateDB, organizations can hold multiple projects and contain multiple CrateDB
products such as CrateDB clusters and EventHub consumers.

To create an organization, run this command:

.. code-block:: console

    sh$ croud organizations create --name CrateOrganization --plan-type 1

If the Croud CLI returns an organization ID, then you have successfully created
your first organization. Also, you automatically have become a member of your
organization. Congratulations!

Validate organization membership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You can validate if you are a member of your organization by running the
following command in the Croud CLI:

.. code-block:: console

    sh$ croud organizations list

The Croud CLI shold now display a list of all the organizations that your user
is a member of.

You have learned how to create create your first organization.

Create your first project
=========================

Now that your first organization is up and running, you can create a project.
The project will let you deploy your first CrateDB cluster and allow you to
group your resources.

.. NOTE::

  Make sure you are logged into your CrateDB Cloud user account.

Create a new project by giving the following command:

.. code-block:: console

    sh$ croud projects create --name demoproject --org-id orgid

Next steps
==========

`Deploy CrateDB cluster`_.

.. _Deploy CrateDB cluster: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/deploy_first_cluster.html
.. _Create your first CrateDB Cloud user account: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/create_account.html
.. _accessed CrateDB Cloud_: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/accessing_cdb_cloud.html
