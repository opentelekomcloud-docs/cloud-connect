:original_name: cc_03_1030.html

.. _cc_03_1030:

Policies
========

Scenarios
---------

Policies record the enterprises routers that have been added to a central network to allow you to better manage your network. You can apply policies of any version.

Constraints
-----------

-  A central network can only have one policy. If you apply another policy for this central network, the policy that was previously applied will be automatically cancelled.
-  In each policy, only one enterprise router can be added for a region. All added enterprise routers can communicate with each other by default.
-  A policy that is being applied or cancelled cannot be deleted.

Creating a Policy
-----------------

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. On the **Policies** tab, click **Add Policy**.

#. Select the target region and enterprise router in that region.

   You can click **Add Enterprise Router** to add an enterprise router in another region.


   .. figure:: /_static/images/en-us_image_0000002446287918.png
      :alt: **Figure 1** Creating a policy

      **Figure 1** Creating a policy

#. Click **OK**.

Applying a Policy
-----------------

#. Log in to the management console.

#. Click |image2| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. On the **Policies** tab, locate the policy you want to apply and click **Apply** on the right.


   .. figure:: /_static/images/en-us_image_0000002483026245.png
      :alt: **Figure 2** Applying a policy

      **Figure 2** Applying a policy

#. In the **Policy Changes** area on the right, check the change of the enterprise router in the policy.

#. Click **OK**.

Deleting a Policy
-----------------

#. Log in to the management console.

#. Click |image3| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. Locate the central network and click its name.

#. On the **Policies** tab, locate the policy you want to delete and click **Delete** on the right.


   .. figure:: /_static/images/en-us_image_0000002449787866.png
      :alt: **Figure 3** Deleting a policy

      **Figure 3** Deleting a policy

#. In the displayed dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000002089584376.png
.. |image2| image:: /_static/images/en-us_image_0000002125143785.png
.. |image3| image:: /_static/images/en-us_image_0000002089584372.png
