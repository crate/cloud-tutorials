.. _edge:

============
CrateDB Edge
============

Crate.io is the hybrid cloud database solution integrating CrateDB clusters 
and the CrateDB Cloud software stack with on-premise or customer-controlled
cloud infrastructure.

The CrateDB Edge concept is simple. You bring your own Kubernetes
infrastructure - whether in a production site, office, laboratory, or local
setup, or in your existing managed cloud infrastructure on AWS, Azure, or GCP.
Wherever it may be, we provide the full experience of CrateDB Cloud to that
Kubernetes environment. You keep your existing infrastructure setup and you 
get all the benefits of CrateDB Cloud on top: from quick deployment to 
seamless scaling and easy cluster management.

The process of getting CrateDB Edge running is far easier than it may seem,
thanks to the support for Edge deployment built into the CrateDB Cloud 
Console, our own web UI. Even so, there are some steps involved, and some
requirements have to be met in order for it to work. This tutorial therefore
serves as an end-to-end walkthrough of the process and prerequisites.

In these tutorials, we first introduce the signup and configuration process 
for a local Kubernetes installation. Next, we explain the process end-to-end
for using AKS and EKS services. After that, we outline the installation method
for some lightweight Kubernetes distributions, like K3s and Microk8s.

Then, we explain how to set up a custom backup location, so you can keep full
ownership of your data backups.

We also introduce a way to monitor your CrateDB Edge cluster in the
visualization tool Grafana coupled with Loki and Prometheus.

.. rubric:: Table of contents

.. toctree::
   :maxdepth: 1

   introduction
   managed-kubernetes
   self-hosted-edge
   custom-backup
   monitoring
