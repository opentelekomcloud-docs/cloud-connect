:original_name: cc_03_0991.html

.. _cc_03_0991:

Creating a User and Granting Central Network Permissions
========================================================

Use IAM to implement fine-grained permissions control for your Cloud Connect resources. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing Cloud Connect resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust an account or cloud service to perform efficient O&M on your Cloud Connect resources.

Skip this part if you do not require individual IAM users for refined permissions management.

:ref:`Figure 1 <cc_03_0991__en-us_topic_0285331217_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719>` shows the process of granting permissions.

Prerequisites
-------------

Before you assign permissions to a user group, you need to know the permissions that you can assign to the user group and select permissions based on service requirements. For details about the system permissions, see :ref:`Permissions <cc_01_0008>`. For the system policies of other services, see `System Permissions <https://docs.otc.t-systems.com/permissions/index.html>`__.

Process Flow
------------

.. _cc_03_0991__en-us_topic_0285331217_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719:

.. figure:: /_static/images/en-us_image_0000002090740630.png
   :alt: **Figure 1** Process of granting permissions

   **Figure 1** Process of granting permissions

#. .. _cc_03_0991__en-us_topic_0285331217_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_li10269636890:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__ (the **Cross Connect Administrator** policy used as an example).

#. `Create an IAM user and add it to a group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__.

   On the IAM console, create a user and add it to the user group created in :ref:`1 <cc_03_0991__en-us_topic_0285331217_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_li10269636890>`.

#. `Log in <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   After logging in to the Cloud Connect console using the user's credentials, verify that the user has all permissions for Cloud Connect resources.

   -  In the service list, choose **Network** > **Cloud Connect**. In the navigation pane on the left, choose **Cloud Connect** > **Central Networks**. Click **Create Central Network** in the upper right corner. If the creation is successful, the **Cross Connect Administrator** policy has taken effect.
   -  Choose any other service in the service list. A message will appear indicating that you have sufficient permissions to access the service.
