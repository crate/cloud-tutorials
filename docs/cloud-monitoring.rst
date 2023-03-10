.. _cloud-monitoring:

Cloud Monitoring
================

This tutorial demonstrates how you can monitor your CrateDB Cloud cluster
using the exposed Prometheus metrics endpoint.

The visualization tool `Grafana`_ is used with `Prometheus`_ to
scrape the API endpoint that exposes metrics and visualize them. The
returned metrics are a sum of all the clusters in the specified organization.

.. rubric:: Table of contents

.. contents::
   :local:

.. _cloud-monitoring-prereqs:

Prerequisites
-------------

- Both Prometheus and Grafana are run as Docker containers in this tutorial, 
  so you need Docker present in your system.

.. cloud-monitoring-deployment:

Cluster Deployment
------------------

The first step is to sign up in the `Cloud Console`_ if you haven't done so
yet. After that, you can :ref:`deploy your cluster <cluster-deployment>`.

Prometheus
----------

Prometheus is used to scrape the CrateDB Cloud API endpoints for available
metrics and serve as a data source for Grafana. 

First, you need to save the following configuration ``.yaml`` file in your
system:

.. code-block::

  # my global config
  global:
    scrape_interval: 15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
    evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
    # scrape_timeout is set to the global default (10s).

  # Alertmanager configuration
  alerting:
    alertmanagers:
      - static_configs:
          - targets:
            # - alertmanager:9093

  # Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
  rule_files:
    # - "first_rules.yml"
    # - "second_rules.yml"

  # A scrape configuration containing exactly one endpoint to scrape:
  # Here it's Prometheus itself.
  scrape_configs:
    - job_name: "cratedb"
      metrics_path: '/api/v2/organizations/{{ORGID}}/metrics/prometheus/'
      basic_auth:
        username: '{{APIKEY}}'
        password: '{{SECRET}}'
      static_configs:
        - targets: ["console.cratedb.cloud"]

Substitute the ``ORGID`` with the ID of your organization. It can be found in
the Settings page in the CrateDB Cloud Console:

.. image:: /_assets/img/cloud-monitoring-org-id.png
   :alt: Organization ID

An API Key and Secret can be generated in your `account page`_ in the CrateDB
Cloud Console.

Once you have added your Organization ID and API credentials, execute the following
command to create a Prometheus instance:

.. code-block:: console

  docker run -d --name prometheus -v /path/to/prometheus.yml:/etc/prometheus/prometheus.yml -p 9090:9090 prom/prometheus

This will start the Prometheus instance exposed on port ``9090``. You can verify 
it's running correctly by visiting ``http://localhost:9090/``. 
On the ``Status -> Targets`` page in the top menu, you should see the
following:

.. image:: /_assets/img/cloud-monitoring-prometheus-verification.png
   :alt: Prometheus targets

There should be an endpoint with your Organization ID with state ``UP``. This
means that Prometheus is able to connect to the API and is scraping the
available metrics.

Available Metrics
-----------------

Most metric semantics are self-explanatory. This list is not exhaustive,
and new metrics can be added at any point in the future. All metrics are per node.


.. list-table::
   :widths: 35 15 50
   :align: left
   :header-rows: 1

   * - Metric
     - Type
     - Description
   * - container_cpu_usage_seconds_total
     - Counter
     - CrateDB CPU usage, in seconds.
   * - container_fs_reads_bytes_total
     - Counter
     - Number of bytes read per disk
   * - container_fs_writes_bytes_total
     - Counter
     - Number of bytes written per disk
   * - container_memory_usage_bytes
     - Gauge
     - Memory usage
   * - container_network_receive_bytes_total
     - Counter
     - Network ingress traffic
   * - container_network_transmit_bytes_total
     - Counter
     - Network egress traffic
   * - crate_circuitbreakers
     - Gauge
     - Circuit breaker stats for crate per breaker
   * - crate_cluster_state_version
     - Gauge
     - Info about the cluster's state
   * - crate_connections
     - Gauge
     - Number of connections per protocol
   * - crate_node
     - Gauge
     - Shard statistics
   * - crate_query_failed_count
     - Counter
     - Number of failed queries per type (i.e. Insert/Select/Update/...)
   * - crate_query_sum_of_durations_millis
     - Counter
     - Sum of the durations of all queries per query type
   * - crate_query_total_count
     - Counter
     - Total number of queries per type
   * - crate_ready
     - Gauge
     - An indicator if this CrateDB node is up-and-running
   * - crate_threadpools
     - Gauge
     - Thread pool statistics, per pool
   * - jvm_*
     - Gauge
     - Various JVM statistics


Grafana
-------

Grafana doesn't need any special configuration. You can run it either in a
Docker container or as a local installation, it doesn't matter for this use
case. Follow the `Grafana documentation`_ and use your preferred method.

By default, Grafana is exposed on port ``3000``. Go to
``http://localhost:3000/`` to access it.

Data source
'''''''''''

Now you can add Prometheus as a data source in Grafana under ``Configuration
-> Data sources``. Choose Prometheus, then use ``http://localhost:9090/`` as the
URL, and leave the rest as default:

.. image:: /_assets/img/cloud-monitoring-prometheus-datasource.png
   :alt: Prometheus data source

.. NOTE::
    If you run both Prometheus and Grafana as Docker containers, you might need to
    create a new network and add both containers to it.

Dashboard
---------

All that's left is to create a dashboard or import one that we prepared for
you. Simply save `this snippet`_ as ``.json`` and import it 
under ``Dashboards -> New -> Import``. Click the "Upload JSON file" and 
choose the file. The dashboard will be called "CrateDB Cluster Monitoring".

.. image:: /_assets/img/cloud-monitoring-grafana-dashboard.png
   :alt: Sample grafana dashboard

The dashboard displays the following metrics. The values are aggregated
from all the running clusters in your organization:

- **Global stats:**
    - Number of nodes

- **Clusters stats:**
    - Type and number of open connections to your clusters
    - SELECT queries per second
    - INSERT queries per second
    - CPU usage (Cores)
    - Memory usage
    - File system writes
    - File system reads

- **Query stats:**
    - Error rate along with the type of failed query
    - Average query duration along with the type of query
    - Queries per second along with the type of query


.. _account page: https://crate.io/docs/cloud/reference/en/latest/api.html
.. _Cloud Console: https://console.cratedb.cloud/?utm_campaign=2022-Q3-WS-Developer-Motion&utm_source=docs
.. _Grafana: https://grafana.com/
.. _Grafana documentation: https://grafana.com/docs/grafana/latest/setup-grafana/installation/
.. _Prometheus: https://grafana.com/oss/prometheus/
.. _this snippet: https://raw.githubusercontent.com/crate/cloud-tutorials/master/docs/_extra/cratedb-cloud-cluster-dashboard.json
