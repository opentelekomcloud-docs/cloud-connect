:original_name: cc_01_0001.html

.. _cc_01_0001:

What Is Cloud Connect?
======================

Cloud Connect provides central networks that allow you to connect Virtual Private Clouds (VPCs) in different regions, so that these VPCs can communicate over a private network as if they were within the same network. Cloud Connect can also work with Direct Connect to set up a hybrid cloud network that enables on-premises data centers to access the VPCs across regions.

.. table:: **Table 1** Cloud Connect features

   +----------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+
   | Feature                                                  | Application Scenarios                                                                                                                  | Bandwidth                                                                                                                                                                                     | Advantages                                                |
   +==========================================================+========================================================================================================================================+===============================================================================================================================================================================================+===========================================================+
   | :ref:`Central Network <cc_01_0001__section118112332502>` | -  Connect VPCs in different regions by attaching them to enterprise routers in the corresponding regions.                             | You need to buy and bind a global connection bandwidth to the central network and assign cross-site connection bandwidths to enable communication between the resources in different regions. | -  Flexible networking                                    |
   |                                                          | -  Connect on-premises data centers to VPCs in different regions by attaching them to enterprise routers in the corresponding regions. |                                                                                                                                                                                               | -  Dynamic routing                                        |
   |                                                          |                                                                                                                                        |                                                                                                                                                                                               | -  A variety of attachments and network scenarios         |
   |                                                          |                                                                                                                                        |                                                                                                                                                                                               | -  Enterprise routers in different regions are connected. |
   +----------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------+

.. _cc_01_0001__section118112332502:

Central Network
---------------

Relying on the cloud backbone network, a central network allows you to easily set up a reliable, intelligent enterprise-grade network and manage global network resources on premises and on the cloud. By setting up a central network, you can enable communication between enterprise routers, in the same region or different regions.

In :ref:`Figure 1 <cc_01_0001__fig8481153843220>`, the two VPCs (VPC-A01 and VPC-A02) are attached to an enterprise router (ER-A) in region A, two VPCs (VPC-B01 and VPC-B02) are attached to an enterprise router (ER-B) in region B, and two VPCs (VPC-C01 and VPC-C02) are attached to an enterprise router (ER-C) in region C.

The three enterprise routers (ER-A, ER-B, and ER-C) are connected over a central network. In this way, the enterprise routers can communicate with each other across regions, and the VPCs in these regions can communicate with each other.

.. _cc_01_0001__fig8481153843220:

.. figure:: /_static/images/en-us_image_0000002445232846.png
   :alt: **Figure 1** How a central network works

   **Figure 1** How a central network works

.. table:: **Table 2** Central network concepts

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Concept                           | Description                                                                                                                                                                                                                     |
   +===================================+=================================================================================================================================================================================================================================+
   | Enterprise router                 | An enterprise router enables the VPCs in the same region to communicate with each other. Enterprise routers in different regions can be connected using a central network to allow for cross-region communication between VPCs. |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Global connection bandwidth       | A global connection bandwidth can be bound to a central network to allow the resources to communicate with each other over the backbone network, regardless of whether:                                                         |
   |                                   |                                                                                                                                                                                                                                 |
   |                                   | -  The resources are in the same geographic region.                                                                                                                                                                             |
   |                                   | -  The resources are in different geographic regions.                                                                                                                                                                           |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Accessing Cloud Connect
-----------------------

You can access Cloud Connect through the management console or by calling HTTPS-based APIs.

-  Using the management console

   The management console is a web-based GUI where you can easily perform various operations. Log in to the management console and choose **Cloud Connect** from the main menu.

-  Using APIs

   If you need to integrate Cloud Connect into a third-party system for secondary development, you can use APIs to access Cloud Connect. For details, see the *Cloud Connect API Reference*.
