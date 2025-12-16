:original_name: cc_03_1103.html

.. _cc_03_1103:

Adding Instances to a Global Connection Bandwidth
=================================================

Scenarios
---------

Central networks can use global connection bandwidths for communication.

Constraints
-----------

-  Instances that can be added to a global connection bandwidth must be from the same region as the bandwidth.
-  A global connection bandwidth can only be used by instances of the same type. If you want another type of instances to use a global connection bandwidth that already has instances, you need to remove the instances first.

   -  You can bind one global connection bandwidth to or unbind it from a central network at a time.

-  To use a global connection bandwidth on a central network, you need to configure cross-site connections by referring to the following:

   -  :ref:`Central Networks <cc_03_1020>`
   -  :ref:`Policies <cc_03_1030>`

Using a Global Connection Bandwidth on a Central Network
--------------------------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner to select a region and a project.
#. In the service list, choose **Network** > **Cloud Connect**.
#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.
#. In the central network list, click the name of the target central network.
#. Click the **Cross-Site Connection Bandwidths** tab.
#. Locate the cross-site connection and click **Assign now** in the **Global Connection Bandwidth** column.
#. On the **Assign Bandwidth** page, select the global connection bandwidth.
#. Specify the bandwidth and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002089104752.png
