:original_name: CreateCentralNetworkPolicy.html

.. _CreateCentralNetworkPolicy:

Adding a Central Network Policy
===============================

Function
--------

This API is used to add a central network policy. A policy cannot be modified. If the policy cannot meet your requirements, you need to add a new policy.

URI
---

POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies

.. table:: **Table 1** Path Parameters

   ================== ========= ====== ===================
   Parameter          Mandatory Type   Description
   ================== ========= ====== ===================
   domain_id          Yes       String Account ID.
   central_network_id Yes       String Central network ID.
   ================== ========= ====== ===================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   ============ ========= ====== ===========
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========
   X-Auth-Token No        String User token.
   ============ ========= ====== ===========

.. table:: **Table 3** Request body parameters

   +---------------------------------+-----------+---------------------------------------------------------------------------------------------------------------+----------------------------------+
   | Parameter                       | Mandatory | Type                                                                                                          | Description                      |
   +=================================+===========+===============================================================================================================+==================================+
   | central_network_policy_document | Yes       | :ref:`CentralNetworkPolicyDocument <createcentralnetworkpolicy__request_centralnetworkpolicydocument>` object | Central network policy document. |
   +---------------------------------+-----------+---------------------------------------------------------------------------------------------------------------+----------------------------------+

.. _createcentralnetworkpolicy__request_centralnetworkpolicydocument:

.. table:: **Table 4** CentralNetworkPolicyDocument

   +---------------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter     | Mandatory | Type                                                                                                                  | Description                                          |
   +===============+===========+=======================================================================================================================+======================================================+
   | default_plane | Yes       | String                                                                                                                | Name of the default central network plane.           |
   +---------------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | planes        | Yes       | Array of :ref:`CentralNetworkPlaneDocument <createcentralnetworkpolicy__request_centralnetworkplanedocument>` objects | List of the central network planes.                  |
   +---------------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | er_instances  | No        | Array of :ref:`AssociateErInstanceDocument <createcentralnetworkpolicy__request_associateerinstancedocument>` objects | List of the enterprise routers on a central network. |
   +---------------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+

.. _createcentralnetworkpolicy__request_centralnetworkplanedocument:

.. table:: **Table 5** CentralNetworkPlaneDocument

   +------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | Parameter              | Mandatory | Type                                                                                                                  | Description                                                                      |
   +========================+===========+=======================================================================================================================+==================================================================================+
   | name                   | Yes       | String                                                                                                                | Instance name.                                                                   |
   +------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | associate_er_tables    | No        | Array of :ref:`AssociateErTableDocument <createcentralnetworkpolicy__request_associateertabledocument>` objects       | List of the enterprise routers on a central network.                             |
   +------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | exclude_er_connections | No        | Array of :ref:`ExcludeErConnectionDocument <createcentralnetworkpolicy__request_excludeerconnectiondocument>` objects | Whether to exclude the connections to enterprise routers on the central network. |
   +------------------------+-----------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+

.. _createcentralnetworkpolicy__request_associateertabledocument:

.. table:: **Table 6** AssociateErTableDocument

   +----------------------------+-----------+--------+------------------------------------------+
   | Parameter                  | Mandatory | Type   | Description                              |
   +============================+===========+========+==========================================+
   | project_id                 | Yes       | String | Project ID.                              |
   +----------------------------+-----------+--------+------------------------------------------+
   | region_id                  | Yes       | String | Region ID.                               |
   +----------------------------+-----------+--------+------------------------------------------+
   | enterprise_router_id       | Yes       | String | Enterprise router ID.                    |
   +----------------------------+-----------+--------+------------------------------------------+
   | enterprise_router_table_id | Yes       | String | ID of the enterprise router route table. |
   +----------------------------+-----------+--------+------------------------------------------+

.. _createcentralnetworkpolicy__request_excludeerconnectiondocument:

.. table:: **Table 7** ExcludeErConnectionDocument

   +-----------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type                                                                                                                  | Description                                                                  |
   +===========+===========+=======================================================================================================================+==============================================================================+
   | [items]   | No        | Array of :ref:`AssociateErInstanceDocument <createcentralnetworkpolicy__request_associateerinstancedocument>` objects | Connections between enterprise routers managed by the central network plane. |
   +-----------+-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+

.. _createcentralnetworkpolicy__request_associateerinstancedocument:

.. table:: **Table 8** AssociateErInstanceDocument

   ==================== ========= ====== =====================
   Parameter            Mandatory Type   Description
   ==================== ========= ====== =====================
   enterprise_router_id Yes       String Enterprise router ID.
   project_id           Yes       String Project ID.
   region_id            Yes       String Region ID.
   ==================== ========= ====== =====================

Response Parameters
-------------------

**Status code: 201**

.. table:: **Table 9** Response body parameters

   +------------------------+------------------------------------------------------------------------------------------------+----------------------------------------+
   | Parameter              | Type                                                                                           | Description                            |
   +========================+================================================================================================+========================================+
   | request_id             | String                                                                                         | Request ID.                            |
   +------------------------+------------------------------------------------------------------------------------------------+----------------------------------------+
   | central_network_policy | :ref:`CentralNetworkPolicy <createcentralnetworkpolicy__response_centralnetworkpolicy>` object | Details of the central network policy. |
   +------------------------+------------------------------------------------------------------------------------------------+----------------------------------------+

.. _createcentralnetworkpolicy__response_centralnetworkpolicy:

.. table:: **Table 10** CentralNetworkPolicy

   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                 | Type                                                                                                           | Description                                                                                                                            |
   +===========================+================================================================================================================+========================================================================================================================================+
   | id                        | String                                                                                                         | Instance ID.                                                                                                                           |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | created_at                | String                                                                                                         | Time when the resource was created. The UTC time is in the *yyyy-MM-ddTHH:mm:ss* format.                                               |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | domain_id                 | String                                                                                                         | ID of the account that the instance belongs to.                                                                                        |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | state                     | String                                                                                                         | Central network policy status.                                                                                                         |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **AVAILABLE**                                                                                                                       |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **CANCELING**                                                                                                                       |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **APPLYING**                                                                                                                        |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **FAILED**                                                                                                                          |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **DELETED**                                                                                                                         |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | central_network_id        | String                                                                                                         | Central network ID.                                                                                                                    |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | document_template_version | String                                                                                                         | Document template version.                                                                                                             |
   |                           |                                                                                                                |                                                                                                                                        |
   |                           |                                                                                                                | -  **2022.08.30**: August 30, 2022                                                                                                     |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | is_applied                | Boolean                                                                                                        | Whether the policy is applied or not.                                                                                                  |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | version                   | Integer                                                                                                        | Version of the central network policy. The version number of the policy is automatically increased by 1 each time a policy is created. |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | document                  | :ref:`CentralNetworkPolicyDocument <createcentralnetworkpolicy__response_centralnetworkpolicydocument>` object | Central network policy document.                                                                                                       |
   +---------------------------+----------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

.. _createcentralnetworkpolicy__response_centralnetworkpolicydocument:

.. table:: **Table 11** CentralNetworkPolicyDocument

   +---------------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter     | Type                                                                                                                   | Description                                          |
   +===============+========================================================================================================================+======================================================+
   | default_plane | String                                                                                                                 | Name of the default central network plane.           |
   +---------------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | planes        | Array of :ref:`CentralNetworkPlaneDocument <createcentralnetworkpolicy__response_centralnetworkplanedocument>` objects | List of the central network planes.                  |
   +---------------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | er_instances  | Array of :ref:`AssociateErInstanceDocument <createcentralnetworkpolicy__response_associateerinstancedocument>` objects | List of the enterprise routers on a central network. |
   +---------------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+

.. _createcentralnetworkpolicy__response_centralnetworkplanedocument:

.. table:: **Table 12** CentralNetworkPlaneDocument

   +------------------------+------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | Parameter              | Type                                                                                                                   | Description                                                                      |
   +========================+========================================================================================================================+==================================================================================+
   | name                   | String                                                                                                                 | Instance name.                                                                   |
   +------------------------+------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | associate_er_tables    | Array of :ref:`AssociateErTableDocument <createcentralnetworkpolicy__response_associateertabledocument>` objects       | List of the enterprise routers on a central network.                             |
   +------------------------+------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | exclude_er_connections | Array of :ref:`ExcludeErConnectionDocument <createcentralnetworkpolicy__response_excludeerconnectiondocument>` objects | Whether to exclude the connections to enterprise routers on the central network. |
   +------------------------+------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+

.. _createcentralnetworkpolicy__response_associateertabledocument:

.. table:: **Table 13** AssociateErTableDocument

   +----------------------------+--------+------------------------------------------+
   | Parameter                  | Type   | Description                              |
   +============================+========+==========================================+
   | project_id                 | String | Project ID.                              |
   +----------------------------+--------+------------------------------------------+
   | region_id                  | String | Region ID.                               |
   +----------------------------+--------+------------------------------------------+
   | enterprise_router_id       | String | Enterprise router ID.                    |
   +----------------------------+--------+------------------------------------------+
   | enterprise_router_table_id | String | ID of the enterprise router route table. |
   +----------------------------+--------+------------------------------------------+

.. _createcentralnetworkpolicy__response_excludeerconnectiondocument:

.. table:: **Table 14** ExcludeErConnectionDocument

   +-----------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+
   | Parameter | Type                                                                                                                   | Description                                                                  |
   +===========+========================================================================================================================+==============================================================================+
   | [items]   | Array of :ref:`AssociateErInstanceDocument <createcentralnetworkpolicy__response_associateerinstancedocument>` objects | Connections between enterprise routers managed by the central network plane. |
   +-----------+------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+

.. _createcentralnetworkpolicy__response_associateerinstancedocument:

.. table:: **Table 15** AssociateErInstanceDocument

   ==================== ====== =====================
   Parameter            Type   Description
   ==================== ====== =====================
   enterprise_router_id String Enterprise router ID.
   project_id           String Project ID.
   region_id            String Region ID.
   ==================== ====== =====================

Example Requests
----------------

Adding a central network policy

.. code-block:: text

   POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies

   {
     "central_network_policy_document" : {
       "default_plane" : "default-plane",
       "planes" : [ {
         "name" : "default-plane"
       } ],
       "er_instances" : [ {
         "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
         "project_id" : "XXX",
         "region_id" : "region-abc"
       } ]
     }
   }

Example Responses
-----------------

**Status code: 201**

The central network policy has been added.

.. code-block::

   {
     "request_id" : "76bfd2b0d492d0e479fbbd3981869c12",
     "central_network_policy" : {
       "id" : "f03478aa-3975-4ca7-9fb2-b49428a01636",
       "created_at" : "2023-10-09T06:22:40.857Z",
       "domain_id" : "XXX",
       "state" : "AVAILABLE",
       "central_network_id" : "e096c86f-817c-418c-945c-6b1d8860a15d",
       "document_template_version" : "2022.08.30",
       "is_applied" : true,
       "version" : 1,
       "document" : {
         "default_plane" : "default-plane",
         "planes" : [ {
           "name" : "default-plane",
           "associate_er_tables" : [ {
             "project_id" : "XXX",
             "region_id" : "region-abc",
             "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
             "enterprise_router_table_id" : "cc542128-5c2d-402a-8960-53bb2ed9484e"
           } ]
         } ],
         "er_instances" : [ {
           "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
           "project_id" : "XXX",
           "region_id" : "region-abc"
         } ]
       }
     }
   }

Status Codes
------------

=========== ==========================================
Status Code Description
=========== ==========================================
201         The central network policy has been added.
=========== ==========================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
