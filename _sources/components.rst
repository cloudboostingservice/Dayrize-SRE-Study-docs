.. _components_page:

Components
=============================================

This section details each component of the monitoring and alerts system.

.. contents:: Table of Contents
   :local:

.. _metrics_section:

Metrics
-------

The following key metrics will be analyzed:

- CPU Usage: Monitoring the application's CPU usage to identify bottlenecks and optimize performance.
- Memory: Monitoring the application's memory usage to detect memory leaks and ensure resource use efficiency.
- Latency: Measuring the application's response time to evaluate user experience and processing speed.
- Traffic: Monitoring the volume of requests and traffic the application receives to identify demand spikes and efficiently scale resources.
- Errors: Tracking the frequency and type of errors occurring in the application to detect issues and improve stability.

.. _data_collection_section:
Data Collection
---------------

- Stackdriver Monitoring will be used to collect the application's metrics on App Engine.
- Terraform will be used to automate the configuration and management of Stackdriver Monitoring resources.

.. _alert_policy_creation_section:
Alert Policy Creation
---------------------

- Custom alert policies will be created for each metric, defining thresholds and conditions that trigger notifications when anomalies are detected.
- Alert policies will be configured to send notifications to a specific Slack channel, allowing relevant teams to receive timely information on critical events.

.. _automation_with_terraform_section:
Automation with Terraform
--------------------------

- Terraform scripts will be used to automate the creation and configuration of:
  - Metrics in Stackdriver Monitoring.
  - Alert policies.
  - Integration with the Slack channel.
