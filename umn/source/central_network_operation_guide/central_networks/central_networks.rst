:original_name: cc_03_1020.html

.. _cc_03_1020:

Central Networks
================

Scenarios
---------

After an enterprise router is created, you can create a central network and add the enterprise router to a policy of the central network. In this way, resources can communicate with each other across regions, and network resources in each region can be managed centrally.

Constraints
-----------

-  Before building a central network, you need to create enterprise routers and enable **Default Route Table Association** and **Default Route Table Propagation** for them.

.. _cc_03_1020__section2954341203415:

Creating a Central Network
--------------------------

#. Log in to the management console.

#. Click |image1| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. In the upper right corner of the page, click **Create Central Network**.

#. Enter the name and description and then configure policies for the central network. :ref:`Table 1 <cc_03_1020__table1866394313519>` describes the parameters required for creating a central network.


   .. figure:: /_static/images/en-us_image_0000002479757549.png
      :alt: **Figure 1** Creating a central network

      **Figure 1** Creating a central network

   .. _cc_03_1020__table1866394313519:

   .. table:: **Table 1** Parameters for creating a central network

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Setting                                                                                                                  |
      +===================================+==========================================================================================================================+
      | Name                              | Enter a name for the central network.                                                                                    |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Describe the central network for easy identification.                                                                    |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Policy                            | -  Region                                                                                                                |
      |                                   |                                                                                                                          |
      |                                   |    Add a policy to record your configuration. You need to select a region for the policy.                                |
      |                                   |                                                                                                                          |
      |                                   | -  Enterprise Router                                                                                                     |
      |                                   |                                                                                                                          |
      |                                   |    Add only one enterprise router for a region. All added enterprise routers can communicate with each other by default. |
      |                                   |                                                                                                                          |
      |                                   |    .. note::                                                                                                             |
      |                                   |                                                                                                                          |
      |                                   |       Please select all the ERs which needs to be connected in one go in Create Central Network page.                    |
      |                                   |                                                                                                                          |
      |                                   |    10 kbit/s of bandwidth is provided for testing connectivity between enterprise routers.                               |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Viewing a Central Network
-------------------------

#. Log in to the management console.

#. Click |image2| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. In the central network list, click the name of the target central network.

#. On the **Basic Information** tab, you can view the details about the central network.


   .. figure:: /_static/images/en-us_image_0000002446788280.png
      :alt: **Figure 2** Viewing the basic information about a central network

      **Figure 2** Viewing the basic information about a central network

Modifying a Central Network
---------------------------

#. Log in to the management console.
#. Click |image3| in the upper left corner to select a region and a project.
#. In the service list, choose **Network** > **Cloud Connect**.
#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.
#. In the central network list, click the name of the target central network.
#. On the **Basic Information** page, you can change the name and description of the central network.

Deleting a Central Network
--------------------------

#. Log in to the management console.

#. Click |image4| in the upper left corner to select a region and a project.

#. In the service list, choose **Network** > **Cloud Connect**.

#. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**.

#. In the central network list, locate the central network you want to delete and click **Delete** in the **Operation** column.

#. In the displayed dialog box, enter **DELETE** to confirm the deletion.


   .. figure:: /_static/images/en-us_image_0000002446790368.png
      :alt: **Figure 3** Deleting a central network

      **Figure 3** Deleting a central network

.. |image1| image:: /_static/images/en-us_image_0000002125143789.png
.. |image2| image:: /_static/images/en-us_image_0000002125143789.png
.. |image3| image:: /_static/images/en-us_image_0000002125143789.png
.. |image4| image:: /_static/images/en-us_image_0000002125143789.png
