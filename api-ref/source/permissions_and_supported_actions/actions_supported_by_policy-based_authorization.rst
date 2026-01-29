:original_name: cc_02_0003.html

.. _cc_02_0003:

Actions Supported by Policy-based Authorization
===============================================

This topic describes the actions supported by Cloud Connect in policy-based authorization.

Supported Actions
-----------------

Cloud Connect provides system-defined policies that can be directly used in IAM. You can also create custom policies to supplement system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: allow or deny operations on specified resources under specific conditions.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions.
-  Actions: specific operations that are allowed or denied.
-  Related actions: actions on which a specific action depends to take effect. When assigning permissions for the action to a user, you also need to assign permissions for the related actions.
-  IAM or enterprise projects: type of projects for which an action will take effect. Policies that contain actions for both IAM and enterprise projects can be used and take effect for both IAM and Enterprise Management. Policies that only contain actions for IAM projects can be used and only take effect for IAM. Administrators can check whether an action supports IAM projects or enterprise projects in the action list. "Y" indicates that the action supports the project and "x" indicates that the action does not support the project.

Cloud Connect supports the following actions in custom policies:

-  :ref:`Central Networks <cc_02_0003__section1554071374415>`: actions supported by all central network APIs, such as the APIs for creating, updating, and deleting a central network, querying central network details, and querying the central network list
-  :ref:`Central Network Policies <cc_02_0003__section1096015764615>`: actions supported by all central network policy APIs, such as the APIs for adding, applying, deleting a central network policy, querying central network policy details, querying the central network policy list, and querying policy changes
-  :ref:`Central Network Connections <cc_02_0003__section13988959134617>`: actions supported by all central network connection APIs, such as the APIs for querying the central network connection list and updating a central network connection

.. _cc_02_0003__section1554071374415:

Central Networks
----------------

.. table:: **Table 1** Actions supported for central networks

   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+
   | Permission                        | API                                                              | Action                   | Related Action | IAM Project | Enterprise Project |
   +===================================+==================================================================+==========================+================+=============+====================+
   | Creating a central network        | POST /v3/{domain_id}/gcn/central-networks                        | cc:centralNetwork:create | ``-``          | Y           | Y                  |
   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+
   | Updating a central network        | PUT /v3/{domain_id}/gcn/central-networks/{central_network_id}    | cc:centralNetwork:update | ``-``          | Y           | Y                  |
   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+
   | Deleting a central network        | DELETE /v3/{domain_id}/gcn/central-networks/{central_network_id} | cc:centralNetwork:delete | ``-``          | Y           | Y                  |
   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+
   | Querying central network details  | GET /v3/{domain_id}/gcn/central-networks/{central_network_id}    | cc:centralNetwork:get    | ``-``          | Y           | Y                  |
   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+
   | Querying the central network list | GET /v3/{domain_id}/gcn/central-networks                         | cc:centralNetwork:list   | ``-``          | Y           | Y                  |
   +-----------------------------------+------------------------------------------------------------------+--------------------------+----------------+-------------+--------------------+

.. _cc_02_0003__section1096015764615:

Central Network Policies
------------------------

.. table:: **Table 2** Actions supported for central network policies

   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+
   | Permission                        | API                                                                                          | Action                          | Related Action | IAM Project | Enterprise Project |
   +===================================+==============================================================================================+=================================+================+=============+====================+
   | Adding a central network policy   | POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies                       | cc:centralNetwork:createPolicy  | ``-``          | Y           | Y                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+
   | Applying a central network policy | POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/apply     | cc:centralNetwork:applyPolicy   | ``-``          | Y           | Y                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+
   | Deleting a central network policy | DELETE /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}         | cc:centralNetwork:deletePolicy  | ``-``          | Y           | Y                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+
   | Querying the central network list | GET /v3/{domain_id}/gcn/central-network/{central_network_id}/policies                        | cc:centralNetwork:listPolicies  | ``-``          | Y           | Y                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+
   | Querying policy changes           | GET /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/change-set | cc:centralNetwork:listChangeSet | ``-``          | Y           | Y                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------+---------------------------------+----------------+-------------+--------------------+

.. _cc_02_0003__section13988959134617:

Central Network Connections
---------------------------

.. table:: **Table 3** Actions supported for central network connections

   +----------------------------------------------+------------------------------------------------------------------------------------------+------------------------------------+----------------+-------------+--------------------+
   | Permission                                   | API                                                                                      | Action                             | Related Action | IAM Project | Enterprise Project |
   +==============================================+==========================================================================================+====================================+================+=============+====================+
   | Querying the central network connection list | GET /v3/{domain_id}/gcn/central-network/{central_network_id}/connections                 | cc:centralNetwork:listConnections  | ``-``          | Y           | Y                  |
   +----------------------------------------------+------------------------------------------------------------------------------------------+------------------------------------+----------------+-------------+--------------------+
   | Updating a central network connection        | PUT /v3/{domain_id}/gcn/central-network/{central_network_id}/connections/{connection_id} | cc:centralNetwork:updateConnection | ``-``          | Y           | Y                  |
   +----------------------------------------------+------------------------------------------------------------------------------------------+------------------------------------+----------------+-------------+--------------------+
