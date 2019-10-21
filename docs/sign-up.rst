
.. _sign-up:

=======
Sign up
=======

Before you can start using :ref:`CrateDB Cloud <index>`, you must first sign
up for a user account.

As a CrateDB Cloud user, you can create and manage organizations and projects.
As an organization administrator, you can also manage other CrateDB Cloud users
as well as launch CrateDB Cloud clusters and other CrateDB Cloud products.


.. rubric:: Table of contents

.. contents::
   :local:


.. _choose-sign-in-method:

Choose a sign-in method
=======================

Visit the `sign in page`_:

.. image:: _assets/img/cloud-sign-in.png

From here, select the sign-in method you want to use. You have two options:

* :ref:`username-password`
* :ref:`azure-ad`


.. _username-password:

Username and password
---------------------

If you select the *Username and password* sign-in method, you should be
presented with a username and password sign in page:

.. image:: _assets/img/cloud-sign-in-user-pass.png

However, before you sign in, you must first sign up for an account.

Select *Sign up* from the bottom of the dialogue box. You will be redirected to
the sign-up page:

.. image:: _assets/img/cloud-sign-up.png

Fill in your details, then select *Sign up*.

Next, you should see this screen:

.. image:: _assets/img/cloud-verification.png

Check your email, fill in the code, and, finally, select *Confirm Account* to
finish the process.


.. _azure-ad:

Azure AD
--------

If you select the *Azure AD* sign-in method, you should be presented
with a `Microsoft Azure`_ *Active Directory* (AD) sign in page:

.. image:: _assets/img/cloud-sign-in-azure-ad.png

You must have a Azure account to proceed.

If you do not have an Azure account, you can `sign up`_ for a one at no cost.
When you're done, come back and continue with the tutorial.


.. _sign-in:

Sign in
=======

Once you're signed in, you should be redirected to the `Cloud Console`_:

.. image:: _assets/img/cloud-first-login.png

There's nothing here yet.

However, by the end of this tutorial, you will have created your first CrateDB
cluster and this page will display important information such as average
response times, queries, logs, and so on.


.. _sign-up-next:

Next steps
==========

Now that you have an account, you can start to interact with CrateDB Cloud.

This tutorial focuses on interacting with CrateDB Cloud using `Croud`_, a
*command-line interface* (CLI) tool. Accordingly, you must :ref:`install and
configure Croud <configure>`.


.. _Cloud Console: https://crate.io/docs/cloud/console/
.. _Croud: https://crate.io/docs/cloud/cli/
.. _sign in page: https://eastus2.azure.cratedb.cloud/
.. _Microsoft Azure: https://azure.microsoft.com/en-us/
.. _sign up: https://azure.microsoft.com/en-us/free/
