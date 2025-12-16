:original_name: cc_03_0889.html

.. _cc_03_0889:

Viewing Central Network Audit Logs
==================================

Scenarios
---------

After CTS is enabled, it starts recording operations on cloud resources. You can view the operation records of the last seven days on the CTS console.

This section describes how you can query or export the operation records of the last seven days on the CTS console.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. In the upper left corner of the page, click |image2| to go to the service list. Under **Management & Deployment**, click **Cloud Trace Service**.

#. In the navigation pane on the left, choose **Trace List**

#. Specify filters as needed. The following filters are available:


   .. figure:: /_static/images/en-us_image_0000002122008564.png
      :alt: **Figure 1** Filters

      **Figure 1** Filters

   -  **Trace Source**, **Resource Type**, and **Search By**

      Select filters from the drop-down list.

      After you select **Trace name** for **Search By**, you also need to select a trace name.

      After you select **Resource ID** for **Search By**, you also need to select or enter a resource ID.

      After you select **Resource name** for **Search By**, you also need to select or enter a resource name.

   -  **Operator**: Select a specific operator (at the user level rather than the tenant level).

   -  **Trace Status**: Select **All trace statuses**, **Normal**, **Warning**, or **Incident**.

   -  Search time range: In the upper right corner, choose **Last 1 hour**, **Last 1 day**, or **Last 1 week**, or specify a custom time range.

#. Click the arrow on the left of the required trace to expand its details.

#. Click **View Trace** in the **Operation** column to view trace details.

.. |image1| image:: /_static/images/en-us_image_0000002157370221.png
.. |image2| image:: /_static/images/en-us_image_0000002121850428.png
