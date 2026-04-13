:original_name: cc_03_1101.html

.. _cc_03_1101:

Overview
========

Global Connection Bandwidth
---------------------------

A global connection bandwidth is used by instances to allow communication over the backbone network.

.. table:: **Table 1** Global connection bandwidth types

   +-------------------+-----------------+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | Bandwidth Type    | Instance Type   | Description                                                                         | Scenario                                                                       |
   +===================+=================+=====================================================================================+================================================================================+
   | Geographic-region | Central network | Select this type of bandwidth if you need communication within a geographic region. | Enterprise routers on a central network must be in the same geographic region. |
   +-------------------+-----------------+-------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+

Constraints on Global Connection Bandwidths
-------------------------------------------

-  Instances that can be added to a global connection bandwidth must be in the same region as the bandwidth.
-  A global connection bandwidth can only be used by instances of the same type. If you want another type of instances to use a global connection bandwidth that already has instances, you need to remove the instances first.
-  To use a global connection bandwidth on a central network, you need to configure cross-site connections by referring to the following:

   -  :ref:`Central Networks <cc_03_1020>`
   -  :ref:`Policies <cc_03_1030>`

-  Before an instance is removed from a global connection bandwidth, ensure the instance is not used to run workloads or establish network connectivity, or the workloads will be unavailable or the network will be interrupted.
-  If a global connection bandwidth has been used to assign cross-site connection bandwidths for a central network, the global connection bandwidth cannot be unbound from the central network. You need to delete the cross-site connection bandwidths first.
-  If a global connection bandwidth is in use by instances, it cannot be deleted.

Geographic-Region Bandwidth Application Scenario (Central Network)
------------------------------------------------------------------

In this example, enterprise routers are connected over a central network.

Enterprise router ER-A in Germany and enterprise router ER-B in Netherlands are from the same geographic region, so a geographic-region bandwidth can be used for communication between the two enterprise routers.


.. figure:: /_static/images/en-us_image_0000002482863093.png
   :alt: **Figure 1** Cross-region communication between enterprise routers

   **Figure 1** Cross-region communication between enterprise routers
