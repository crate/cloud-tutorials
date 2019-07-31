.. highlights:: console

=====================================
Create first Organization and Project
=====================================

During the preceding chapters of this CrateDB Cloud getting started guide, you
have created your `CrateDB Cloud user account`_ and `accessed CrateDB Cloud`_.

Create your first organization
==============================

In this section you will learn how to create your first organization.
In CrateDB, organizations can hold multiple projects.

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
Your project then allows you to deploy your first CrateDB cluster. Also projects
let you group your resources. An organization can hold multiple projects and a project can contain multiple products, such as CrateDB Clusters or EventHub Consumers. For example, you might want to have one project for development purposes and another one for your production setup. Projects simply allow you to separate your environments (...).

If you aren’t logged in already, run:
$ croud login
Once authenticated we can create a new project by entering the following command:
$ croud projects create --name demoproject --org-id orgid
Let’s take demoproject for our project name and as --org-id we enter the organization id of the organization we created in the previous video.
Once you hit enter you get the name and project-id of the newly created project returned (...). Great! You’ve successfully created your first project.


Next steps
==========

`Deploy CrateDB cluster`_.

.. _Deploy CrateDB cluster: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/deploy_first_cluster.html
.. _Create your first CrateDB Cloud user account: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/create_account.html
.. _accessed CrateDB Cloud_: https://crate.io/docs/crate/cloud-getting-started/en/latest/create/accessing_cdb_cloud.html
