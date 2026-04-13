:original_name: cc_03_1104.html

.. _cc_03_1104:

Removing Instances from a Global Connection Bandwidth
=====================================================

Scenarios
---------

You can unbind a global connection bandwidth from a central network.

Constraints
-----------

-  Before an instance is removed from a global connection bandwidth, the instance is not used to run workloads or establish network connectivity, or the workloads will be unavailable or the network will be interrupted.
-  A global connection bandwidth can only be used by one type of instances. If you want to change the instance type, remove all the instances from the global connection bandwidth and then add instances of another type by referring to :ref:`Adding Instances to a Global Connection Bandwidth <cc_03_1103>`.
-  If a global connection bandwidth has been used to assign cross-site connection bandwidths for a central network, the global connection bandwidth cannot be unbound from the central network. You need to delete the cross-site connection bandwidths first.

Deleting Cross-Site Connection Bandwidth
----------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner to select a region and a project.
#. In the service list, choose **Network** > **Cloud Connect**.
#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.
#. In the central network list, click the name of the target central network.
#. Click the **Cross-Site Connection Bandwidths** tab.
#. Locate the cross-site connection and click **Delete Bandwidth** in the **Operation** column.
#. In the displayed dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002089104748.png
