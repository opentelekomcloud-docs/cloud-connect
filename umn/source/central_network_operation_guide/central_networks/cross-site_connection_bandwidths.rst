:original_name: cc_03_1050.html

.. _cc_03_1050:

Cross-Site Connection Bandwidths
================================

Scenarios
---------

Enterprise routers in different regions added to the same policy can communicate with each other after you purchase a global connection bandwidth and assign cross-site connection bandwidths for these network resources.

Constraints
-----------

-  :ref:`Changing Cross-Site Connection Bandwidth <cc_03_1050__section1734561716011>` and :ref:`Deleting a Cross-Site Connection Bandwidth <cc_03_1050__section658814195716>` cannot be performed when a cross-site connection is being created, updated, deleted, frozen, unfrozen, or is recovering.
-  The total of cross-site connection bandwidths cannot exceed the global connection bandwidth.
-  Cross site connection bandwidths are displayed only when a central network is created with at least 2 enterprise routers (1 per region) under policies.

.. _cc_03_1050__section6858346105817:

Assigning a Cross-Site Connection Bandwidth
-------------------------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. Click the **Cross-Site Connection Bandwidths** tab.

#. Locate the cross-site connection and click **Assign now** in the **Global Connection Bandwidth** column.

#. On the **Assign Bandwidth** page, select the global connection bandwidth.

   You can also click **create Now** if there are no available global connection bandwidths.


   .. figure:: /_static/images/en-us_image_0000002446606818.png
      :alt: **Figure 1** Assigning a cross-site connection bandwidth

      **Figure 1** Assigning a cross-site connection bandwidth

#. Enter the bandwidth.

#. Click **OK**.

Viewing Monitoring Metrics of Cross-Site Connection Bandwidths
--------------------------------------------------------------

You can view the status of each cross-site connection bandwidth assigned for communication between network resources.

#. Log in to the management console.

#. Click |image2| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. Switch to the **Cross-Site Connection Bandwidths** tab and click the icon in the **Monitoring** column to view the monitoring data.


   .. figure:: /_static/images/en-us_image_0000002449948666.png
      :alt: **Figure 2** Cross-site connection bandwidth monitoring

      **Figure 2** Cross-site connection bandwidth monitoring

.. note::

   By setting up a central network, you can enable communications between enterprise routers in the same region or across regions. When a central network is used, attachments on the enterprise routers used in the central network policy will be monitored. For details about monitoring, see :ref:`Central Network Metrics <cc_03_0884>`.

.. _cc_03_1050__section1734561716011:

Changing Cross-Site Connection Bandwidth
----------------------------------------

#. Log in to the management console.

#. Click |image3| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. Click the **Cross-Site Connection Bandwidths** tab.

#. Locate the cross-site connection and click **Change Bandwidth** in the **Operation** column.

#. In the displayed dialog box, change the global connection bandwidth of the cross-site connection.

   You can also change the bandwidth of the cross-site connection.


   .. figure:: /_static/images/en-us_image_0000002449789746.png
      :alt: **Figure 3** Modifying a bandwidth

      **Figure 3** Modifying a bandwidth

#. Click **OK**.

.. _cc_03_1050__section658814195716:

Deleting a Cross-Site Connection Bandwidth
------------------------------------------

#. Log in to the management console.

#. Click |image4| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. Click the **Cross-Site Connection Bandwidths** tab.

#. Locate the cross-site connection and click **Delete Bandwidth** in the **Operation** column.

#. In the displayed dialog box, click **OK**.


   .. figure:: /_static/images/en-us_image_0000002449949814.png
      :alt: **Figure 4** Deleting a cross-site connection bandwidth

      **Figure 4** Deleting a cross-site connection bandwidth

#. Click **Go to Delete** to delete the global connection bandwidth if you no longer need it to avoid unnecessary charges.


   .. figure:: /_static/images/en-us_image_0000002461583304.png
      :alt: **Figure 5** Confirming whether to delete the global connection bandwidth

      **Figure 5** Confirming whether to delete the global connection bandwidth

.. note::

   After you delete a cross-site connection bandwidth, you still need to pay for the global connection bandwidth.

.. |image1| image:: /_static/images/en-us_image_0000002125143777.png
.. |image2| image:: /_static/images/en-us_image_0000002089584360.png
.. |image3| image:: /_static/images/en-us_image_0000002125143773.png
.. |image4| image:: /_static/images/en-us_image_0000002089584348.png
