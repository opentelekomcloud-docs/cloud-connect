:original_name: cc_03_1102.html

.. _cc_03_1102:

Creating a Global Connection Bandwidth
======================================

Scenarios
---------

This section describes how to create a global connection bandwidth for communication over the backbone network.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Intra-Cloud** > **Global Connection Bandwidths**.

#. Click **Create Global Connection Bandwidth**.

#. Configure the parameters based on :ref:`Table 1 <cc_03_1102__table9908161616>`.


   .. figure:: /_static/images/en-us_image_0000002480095461.png
      :alt: **Figure 1** Creating a global connection bandwidth

      **Figure 1** Creating a global connection bandwidth

   .. _cc_03_1102__table9908161616:

   .. table:: **Table 1** Parameters required for creating a global connection bandwidth

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                               |
      +===================================+===========================================================================================================================================================+
      | Bandwidth Type                    | Mandatory                                                                                                                                                 |
      |                                   |                                                                                                                                                           |
      |                                   | Only geographic-region bandwidths are supported. You need to select a geographic region and specify the regions that need to communicate with each other. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Geographic Region                 | Only **Europe** is supported if **Geographic-region** is selected for **Bandwidth Type**.                                                                 |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Connect Regions                   | Regions that need to communicate with each other in a geographic region.                                                                                  |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Billed By                         | Mandatory                                                                                                                                                 |
      |                                   |                                                                                                                                                           |
      |                                   | The price of a global connection bandwidth varies by its size.                                                                                            |
      |                                   |                                                                                                                                                           |
      |                                   | -  After a bandwidth is purchased, the billing starts immediately regardless of whether the bandwidth is used.                                            |
      |                                   | -  If a bandwidth is no longer required, delete it in a timely manner to avoid unnecessary fees.                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Bandwidth                         | Mandatory                                                                                                                                                 |
      |                                   |                                                                                                                                                           |
      |                                   | Select the bandwidth, in Mbit/s.                                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Bandwidth Name                    | Mandatory                                                                                                                                                 |
      |                                   |                                                                                                                                                           |
      |                                   | Enter the name of the bandwidth. The name:                                                                                                                |
      |                                   |                                                                                                                                                           |
      |                                   | -  Must contain 1 to 64 characters.                                                                                                                       |
      |                                   | -  Can contain letters, digits, underscores (_), hyphens (-), and periods (.).                                                                            |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enterprise Project                | Mandatory                                                                                                                                                 |
      |                                   |                                                                                                                                                           |
      |                                   | Provides a cloud resource management mode, in which cloud resources and members are centrally managed by project.                                         |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Next**.

#. Confirm the configurations and click **Submit**.

   The global connection bandwidth list page is displayed.

#. In the global connection bandwidth list, view the status of the bandwidth.

   If the bandwidth status becomes **Normal**, the creation is successful.

.. |image1| image:: /_static/images/en-us_image_0000002089264608.png
