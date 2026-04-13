:original_name: cc_01_0008.html

.. _cc_01_0008:

Permissions
===========

If you need to assign different permissions to employees in your enterprise, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM allows you to control access to your Cloud Connect resources.

With IAM, you can create IAM users for certain employees in your enterprise and assign permissions to control their access to Cloud Connect resources. For example, you can assign permissions to software developers so that they use Cloud Connect but cannot delete Cloud Connect resources or perform any other high-risk operations.

Skip this part if you do not require individual IAM users for refined permissions management.

IAM is a free service. For more information about IAM, see the `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__

Cloud Connect Permissions
-------------------------

By default, new IAM users do not have permissions assigned. To assign permissions to these new users, add them to one or more groups and attach permissions policies or roles to these groups.

Cloud Connect is a global service for access from any region. You can assign IAM permissions to users in the global service project. In this way, users do not need to switch regions when they access IAM.

You can grant permissions by using roles or policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions based on user responsibility. This mechanism provides only a limited number of service-level roles. When using roles to grant permissions, you may need to also assign other dependency roles. Roles are not an ideal choice for fine-grained authorization.
-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, the administrator can grant Cloud Connect users only the permissions for managing cloud connections.

:ref:`Table 1 <cc_01_0008__en-us_topic_0173524723_en-us_topic_0173475706_en-us_topic_0170232209_table481412518317>` lists the system-defined roles or policies supported by Cloud Connect.

.. _cc_01_0008__en-us_topic_0173524723_en-us_topic_0173475706_en-us_topic_0170232209_table481412518317:

.. table:: **Table 1** Cloud Connect system-defined roles or policies

   +-------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------+
   | System Role/Policy Name       | Description                                                                                                                                                                                                                    | Type                  | Dependency                                                                                  |
   +===============================+================================================================================================================================================================================================================================+=======================+=============================================================================================+
   | Cross Connect Administrator   | Administrator permissions for Cloud Connect. Users with this role must also have the **Tenant Guest** and **VPC Administrator** permissions.                                                                                   | System-defined role   | **Tenant Guest** and **VPC Administrator**                                                  |
   |                               |                                                                                                                                                                                                                                |                       |                                                                                             |
   |                               | .. note::                                                                                                                                                                                                                      |                       | -  **VPC Administrator**: project-level policy, which must be assigned for the same project |
   |                               |                                                                                                                                                                                                                                |                       | -  **Tenant Guest**: project-level policy, which must be assigned for the same project      |
   |                               |    Users who have these permissions can only view Cloud Connect resources. You are advised to use the **CC FullAccess** policy.                                                                                                |                       |                                                                                             |
   +-------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------+
   | CC FullAccess                 | All permissions on Cloud Connect.                                                                                                                                                                                              | System-defined policy | CC Network Depend QueryAccess                                                               |
   +-------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------+
   | CC ReadOnlyAccess             | Read-only permissions for Cloud Connect. Users who have these permissions can only view Cloud Connect resources.                                                                                                               | System-defined policy | ``-``                                                                                       |
   +-------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------+
   | CC Network Depend QueryAccess | Read-only permissions required to access dependency resources when using Cloud Connect.                                                                                                                                        | System-defined policy | ``-``                                                                                       |
   |                               |                                                                                                                                                                                                                                |                       |                                                                                             |
   |                               | Users who have these permissions can view VPCs.                                                                                                                                                                                |                       |                                                                                             |
   |                               |                                                                                                                                                                                                                                |                       |                                                                                             |
   |                               | .. note::                                                                                                                                                                                                                      |                       |                                                                                             |
   |                               |                                                                                                                                                                                                                                |                       |                                                                                             |
   |                               |    If you only have the **CC FullAccess** permission, you cannot select **Enterprise Router** on the console. In this case, you need the **CC Network Depend QueryAccess**, **Tenant Guest**, or **ER FullAccess** permission. |                       |                                                                                             |
   +-------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------+

:ref:`Table 2 <cc_01_0008__table13641113421711>` lists common operations supported by each system-defined role.

.. note::

   When you configure system policies **CC FullAccess** and **CC ReadOnlyAccess**, select **Global services** for **Scope**. In this case, the two system policies can take effect for resources such as network instances, inter-domain bandwidths, and routes.

.. _cc_01_0008__table13641113421711:

.. table:: **Table 2** Common operations supported by system-defined permissions

   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Operation                              | Cross Connect Administrator | CC FullAccess | CC ReadOnlyAccess | CC Network Depend QueryAccess |
   +========================================+=============================+===============+===================+===============================+
   | Creating a central network             | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Updating a central network             | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Deleting a central network             | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying details of a central network  | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying central networks              | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Adding a central network policy        | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Applying a central network policy      | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Deleting a central network policy      | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying central network policies      | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying policy changes                | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying central network connections   | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Updating a central network connection  | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying quotas                        | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying the capabilities              | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Creating a global connection bandwidth | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Updating a global connection bandwidth | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Querying a global connection bandwidth | Y                           | Y             | Y                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
   | Deleting a global connection bandwidth | x                           | Y             | x                 | x                             |
   +----------------------------------------+-----------------------------+---------------+-------------------+-------------------------------+
