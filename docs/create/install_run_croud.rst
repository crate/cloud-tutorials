.. highlights:: console

=============================
Install and Run The Croud CLI
=============================

You have completed the preceding step :ref:`creating_cloud_user_account`. Let's
now install the Croud CLI. The Croud CLI is the  dedicated command line
interface (CLI) that you will use to manage your CrateDB Cloud organizations,
projects, and resources.

Prerequisites
=============

Python version 3.6 or higher is installed on your system.

Python
======

Visit `python.org/downloads`_ for the latest Python package.

Installing the Croud CLI
========================

At this point you should have Python installed on your system, which makes you
ready to install the Croud CLI.

To install the Croud CLI, start the command line tool on your system and run:

.. code-block:: console

    sh$ python3 -m pip install --user -U croud

The Croud CLI should now be installed.

To assure you that the installation was successful, run:

.. code-block:: console

    sh$ croud -v

If it all went well, your command line should display the version number of the
Croud CLI.

<SCREENSHOT>

You have successfully installed the CrateDB Croud CLI.

Updating the Croud CLI
----------------------

To get the latest Croud CLI version and features run:

.. code-block:: console

    sh$ pip install -U croud

Next steps
==========



.. _python.org/downloads: https://www.python.org/downloads/
