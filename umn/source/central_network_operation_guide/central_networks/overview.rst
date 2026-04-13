:original_name: cc_03_1010.html

.. _cc_03_1010:

Overview
========

Central Network
---------------

Relying on the cloud backbone network, a central network allows you to easily set up a reliable, intelligent enterprise-grade network and manage global network resources on premises and on the cloud. By setting up a central network, you can enable communication between enterprise routers, in the same region or different regions.

Application Scenarios
---------------------

-  Cross-region communication on the cloud: Enterprise routers in different regions are added to a central network as attachments so that resources in these regions can communicate with each other over one network.


   .. figure:: /_static/images/en-us_image_0000002445430860.png
      :alt: **Figure 1** Cross-region communication between enterprise routers

      **Figure 1** Cross-region communication between enterprise routers

-  Global network: By flexibly changing the central network policies, you can build a global network more conveniently.

Central Network Constraints
---------------------------

-  To use a central network, the following resources must have been created:

   -  Enterprise router: used to set up a central network

      .. note::

         If you are not the owner of an enterprise router, you cannot use the enterprise router to set up a central network.

-  Policy management

   -  A central network can only have one policy. If you apply another policy for this central network, the policy that was previously applied will be automatically cancelled.
   -  In each policy, only one enterprise router can be added for a region. All added enterprise routers can communicate with each other by default.
   -  A policy that is being applied or cancelled cannot be deleted.

-  Cross-site connection bandwidth management

   -  A cross-site connection bandwidth cannot be changed or deleted when it is being created, updated, deleted, frozen, unfrozen, or is recovering.
   -  The total of cross-site connection bandwidths cannot exceed the global connection bandwidth.
   -  If a cross-site connection bandwidth is deleted, you will still be billed for the global connection bandwidth.

Configuration Process
---------------------

:ref:`Figure 2 <cc_03_1010__fig1846518181211>` shows the process of configuring a central network to manage global network resources.

.. _cc_03_1010__fig1846518181211:

.. figure:: /_static/images/en-us_image_0000002478587813.png
   :alt: **Figure 2** Central network configuration process

   **Figure 2** Central network configuration process

.. table:: **Table 1** Steps for configuring a central network

   +-----+-----------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
   | No. | Step                                    | Description                                                                                                                                                                                                                                                                     | Reference                                                                             |
   +=====+=========================================+=================================================================================================================================================================================================================================================================================+=======================================================================================+
   | 1   | Create a central network.               | After an enterprise router is created, you can create a central network and add the enterprise router to a policy of the central network. In this way, resources can communicate with each other across regions, and network resources in each region can be managed centrally. | :ref:`Creating a Central Network <cc_03_1020__section2954341203415>`                  |
   +-----+-----------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
   | 2   | Assign cross-site connection bandwidth. | After adding enterprise routers in different regions to the same policy, purchase a global connection bandwidth and assign a bandwidth for cross-site connections.                                                                                                              | :ref:`Assigning a Cross-Site Connection Bandwidth <cc_03_1050__section6858346105817>` |
   +-----+-----------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
