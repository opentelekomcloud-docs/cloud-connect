:original_name: ApplyCentralNetworkPolicy.html

.. _ApplyCentralNetworkPolicy:

Applying a Central Network Policy
=================================

Function
--------

This API is used to apply a central network policy.

URI
---

POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/apply

.. table:: **Table 1** Path Parameters

   ================== ========= ====== ==========================
   Parameter          Mandatory Type   Description
   ================== ========= ====== ==========================
   domain_id          Yes       String Account ID.
   policy_id          Yes       String Central network policy ID.
   central_network_id Yes       String Central network ID.
   ================== ========= ====== ==========================

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   ============ ========= ====== ===========
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========
   X-Auth-Token No        String User token.
   ============ ========= ====== ===========

Response Parameters
-------------------

**Status code: 202**

.. table:: **Table 3** Response body parameters

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | Parameter                         | Type                                                                                                                            | Description                             |
   +===================================+=================================================================================================================================+=========================================+
   | request_id                        | String                                                                                                                          | Request ID.                             |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | central_network_policy            | :ref:`CentralNetworkPolicy <applycentralnetworkpolicy__response_centralnetworkpolicy>` object                                   | Details of the central network policy.  |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | central_network_policy_change_set | Array of :ref:`CentralNetworkElementChangeEntry <applycentralnetworkpolicy__response_centralnetworkelementchangeentry>` objects | List of central network policy changes. |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+

.. _applycentralnetworkpolicy__response_centralnetworkpolicy:

.. table:: **Table 4** CentralNetworkPolicy

   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                 | Type                                                                                                          | Description                                                                                                                            |
   +===========================+===============================================================================================================+========================================================================================================================================+
   | id                        | String                                                                                                        | Instance ID.                                                                                                                           |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | created_at                | String                                                                                                        | Time when the resource was created. The UTC time is in the *yyyy-MM-ddTHH:mm:ss* format.                                               |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | domain_id                 | String                                                                                                        | ID of the account that the instance belongs to.                                                                                        |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | state                     | String                                                                                                        | Central network policy status.                                                                                                         |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **AVAILABLE**                                                                                                                       |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **CANCELING**                                                                                                                       |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **APPLYING**                                                                                                                        |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **FAILED**                                                                                                                          |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **DELETED**                                                                                                                         |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | central_network_id        | String                                                                                                        | Central network ID.                                                                                                                    |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | document_template_version | String                                                                                                        | Document template version.                                                                                                             |
   |                           |                                                                                                               |                                                                                                                                        |
   |                           |                                                                                                               | -  **2022.08.30**: August 30, 2022                                                                                                     |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | is_applied                | Boolean                                                                                                       | Whether the policy is applied or not.                                                                                                  |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | version                   | Integer                                                                                                       | Version of the central network policy. The version number of the policy is automatically increased by 1 each time a policy is created. |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
   | document                  | :ref:`CentralNetworkPolicyDocument <applycentralnetworkpolicy__response_centralnetworkpolicydocument>` object | Central network policy document.                                                                                                       |
   +---------------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

.. _applycentralnetworkpolicy__response_centralnetworkpolicydocument:

.. table:: **Table 5** CentralNetworkPolicyDocument

   +---------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | Parameter     | Type                                                                                                                  | Description                                          |
   +===============+=======================================================================================================================+======================================================+
   | default_plane | String                                                                                                                | Name of the default central network plane.           |
   +---------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | planes        | Array of :ref:`CentralNetworkPlaneDocument <applycentralnetworkpolicy__response_centralnetworkplanedocument>` objects | List of the central network planes.                  |
   +---------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+
   | er_instances  | Array of :ref:`AssociateErInstanceDocument <applycentralnetworkpolicy__response_associateerinstancedocument>` objects | List of the enterprise routers on a central network. |
   +---------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------+

.. _applycentralnetworkpolicy__response_centralnetworkplanedocument:

.. table:: **Table 6** CentralNetworkPlaneDocument

   +------------------------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | Parameter              | Type                                                                                                                  | Description                                                                      |
   +========================+=======================================================================================================================+==================================================================================+
   | name                   | String                                                                                                                | Instance name.                                                                   |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | associate_er_tables    | Array of :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` objects       | List of the enterprise routers on a central network.                             |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+
   | exclude_er_connections | Array of :ref:`ExcludeErConnectionDocument <applycentralnetworkpolicy__response_excludeerconnectiondocument>` objects | Whether to exclude the connections to enterprise routers on the central network. |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------+

.. _applycentralnetworkpolicy__response_centralnetworkelementchangeentry:

.. table:: **Table 7** CentralNetworkElementChangeEntry

   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Parameter                            | Type                                                                                                                    | Description                                                                                                      |
   +======================================+=========================================================================================================================+==================================================================================================================+
   | operation_id                         | String                                                                                                                  | Instance status.                                                                                                 |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **CreateCentralNetworkPlane**: adds a central network plane.                                                  |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **DeleteCentralNetworkPlane**: removes a central network plane.                                               |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **UpdateCentralNetworkPlane**: updates a central network plane.                                               |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **CreateCentralNetworkErInstance**: adds an enterprise router as an attachment on a central network.          |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **DeleteCentralNetworkErInstance**: removes an enterprise router from a central network.                      |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **CreateCentralNetworkErConnection**: creates a connection between enterprise routers on a central network.   |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **DeleteCentralNetworkErConnection**: deletes a connection between enterprise routers from a central network. |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **CreateCentralNetworkErTable**: adds an enterprise router route table as an attachment on a central network. |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **DeleteCentralNetworkErTable**: removes an enterprise router route table from a central network.             |
   |                                      |                                                                                                                         |                                                                                                                  |
   |                                      |                                                                                                                         | -  **SwitchCentralNetworkErTable**: changes an enterprise router route table on a central network.               |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <applycentralnetworkpolicy__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | original_central_network_plane       | :ref:`CentralNetworkPlaneChangeDocument <applycentralnetworkpolicy__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | newest_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <applycentralnetworkpolicy__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <applycentralnetworkpolicy__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_instance   | :ref:`AssociateErInstanceDocument <applycentralnetworkpolicy__response_associateerinstancedocument>` object             | Details of the central network.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_instance   | :ref:`AssociateErInstanceDocument <applycentralnetworkpolicy__response_associateerinstancedocument>` object             | Details of the central network.                                                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | central_network_plane_name           | String                                                                                                                  | Name of the central network plane.                                                                               |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_connection | Array of :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` objects         | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_connection | Array of :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` objects         | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_table      | :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` object                   | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_table      | :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` object                   | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | switch_central_network_er_table      | :ref:`SwitchErTableDocument <applycentralnetworkpolicy__response_switchertabledocument>` object                         | Policy document for changing the enterprise router route table.                                                  |
   +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+

.. _applycentralnetworkpolicy__response_centralnetworkplanechangedocument:

.. table:: **Table 8** CentralNetworkPlaneChangeDocument

   +------------------------+-----------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | Parameter              | Type                                                                                                                  | Description                                                                    |
   +========================+=======================================================================================================================+================================================================================+
   | name                   | String                                                                                                                | Instance name.                                                                 |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | is_default             | Boolean                                                                                                               | Whether the plane is the default one.                                          |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | associate_er_tables    | Array of :ref:`AssociateErTableDocument <applycentralnetworkpolicy__response_associateertabledocument>` objects       | List of the enterprise routers on a central network.                           |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | exclude_er_connections | Array of :ref:`ExcludeErConnectionDocument <applycentralnetworkpolicy__response_excludeerconnectiondocument>` objects | Whether to exclude the connections to enterprise routers on a central network. |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+

.. _applycentralnetworkpolicy__response_excludeerconnectiondocument:

.. table:: **Table 9** ExcludeErConnectionDocument

   +-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+
   | Parameter | Type                                                                                                                  | Description                                                                  |
   +===========+=======================================================================================================================+==============================================================================+
   | [items]   | Array of :ref:`AssociateErInstanceDocument <applycentralnetworkpolicy__response_associateerinstancedocument>` objects | Connections between enterprise routers managed by the central network plane. |
   +-----------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+

.. _applycentralnetworkpolicy__response_associateerinstancedocument:

.. table:: **Table 10** AssociateErInstanceDocument

   ==================== ====== =====================
   Parameter            Type   Description
   ==================== ====== =====================
   enterprise_router_id String Enterprise router ID.
   project_id           String Project ID.
   region_id            String Region ID.
   ==================== ====== =====================

.. _applycentralnetworkpolicy__response_associateertabledocument:

.. table:: **Table 11** AssociateErTableDocument

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

.. _applycentralnetworkpolicy__response_switchertabledocument:

.. table:: **Table 12** SwitchErTableDocument

   +-------------------------------------+--------+-----------------------------------------------------------------+
   | Parameter                           | Type   | Description                                                     |
   +=====================================+========+=================================================================+
   | project_id                          | String | Project ID.                                                     |
   +-------------------------------------+--------+-----------------------------------------------------------------+
   | region_id                           | String | Region ID.                                                      |
   +-------------------------------------+--------+-----------------------------------------------------------------+
   | enterprise_router_id                | String | Enterprise router ID.                                           |
   +-------------------------------------+--------+-----------------------------------------------------------------+
   | original_enterprise_router_table_id | String | Specifies the route table ID of the original enterprise router. |
   +-------------------------------------+--------+-----------------------------------------------------------------+
   | new_enterprise_router_table_id      | String | Specifies the route table ID of the new enterprise router.      |
   +-------------------------------------+--------+-----------------------------------------------------------------+

Example Requests
----------------

Applying a central network policy

.. code-block:: text

   POST /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/apply

Example Responses
-----------------

**Status code: 202**

The central network policy has been applied.

.. code-block::

   {
     "request_id" : "edb137a2c46c5bda0409833359bb649b",
     "central_network_policy" : {
       "id" : "ff51f460-4bbe-4385-b2c4-efbe3318076f",
       "created_at" : "2023-10-09T07:00:33.663Z",
       "domain_id" : "XXX",
       "state" : "APPLYING",
       "central_network_id" : "e096c86f-817c-418c-945c-6b1d8860a15d",
       "document_template_version" : "2022.08.30",
       "is_applied" : false,
       "version" : 2,
       "document" : {
         "default_plane" : "default-plane",
         "planes" : [ {
           "name" : "default-plane",
           "associate_er_tables" : [ {
             "project_id" : "XXX",
             "region_id" : "region-abc",
             "enterprise_router_id" : "c73b26b7-33f0-438d-b440-8e87dfe6fef9",
             "enterprise_router_table_id" : "c0d51f20-0313-40f7-a74e-9dccb5da21c0"
           } ]
         } ],
         "er_instances" : [ {
           "enterprise_router_id" : "c73b26b7-33f0-438d-b440-8e87dfe6fef9",
           "project_id" : "XXX",
           "region_id" : "region-abc"
         } ]
       }
     },
     "central_network_policy_change_set" : [ {
       "operation_id" : "UpdateCentralNetworkPlane",
       "original_central_network_plane" : {
         "name" : "default-plane",
         "is_default" : true,
         "associate_er_tables" : [ {
           "project_id" : "XXX",
           "region_id" : "region-abc",
           "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
           "enterprise_router_table_id" : "cc542128-5c2d-402a-8960-53bb2ed9484e"
         } ]
       },
       "newest_central_network_plane" : {
         "name" : "default-plane",
         "is_default" : true,
         "associate_er_tables" : [ {
           "project_id" : "XXX",
           "region_id" : "region-abc",
           "enterprise_router_id" : "c73b26b7-33f0-438d-b440-8e87dfe6fef9",
           "enterprise_router_table_id" : "c0d51f20-0313-40f7-a74e-9dccb5da21c0"
         } ]
       }
     }, {
       "operation_id" : "CreateCentralNetworkErInstance",
       "create_central_network_er_instance" : {
         "enterprise_router_id" : "c73b26b7-33f0-438d-b440-8e87dfe6fef9",
         "project_id" : "XXX",
         "region_id" : "region-abc"
       }
     }, {
       "operation_id" : "DeleteCentralNetworkErInstance",
       "delete_central_network_er_instance" : {
         "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
         "project_id" : "XXX",
         "region_id" : "region-abc"
       }
     }, {
       "operation_id" : "CreateCentralNetworkErConnection",
       "central_network_plane_name" : "default-plane",
       "index" : 0,
       "create_central_network_er_connection" : [ {
         "project_id" : "XXX",
         "region_id" : "region-abc-1",
         "enterprise_router_id" : "c9c9c756-6984-4866-bab7-5b55c81594bd",
         "enterprise_router_table_id" : "58613052-f9d4-4fa4-a3f0-6d6873190826"
       }, {
         "project_id" : "8d01a037388442f6a2e435f4f30860a3",
         "region_id" : "region-abc-2",
         "enterprise_router_id" : "58fad9c1-b4bd-4622-84e4-a0fcb2423601",
         "enterprise_router_table_id" : "a5347056-e29f-4192-9256-e151c61f854c"
       } ]
     }, {
       "operation_id" : "DeleteCentralNetworkErConnection",
       "central_network_plane_name" : "default-plane",
       "index" : 1,
       "delete_central_network_er_connection" : [ {
         "project_id" : "XXX",
         "region_id" : "region-abc-1",
         "enterprise_router_id" : "c9c9c756-6984-4866-bab7-5b55c81594bd",
         "enterprise_router_table_id" : "58613052-f9d4-4fa4-a3f0-6d6873190826"
       }, {
         "project_id" : "8d01a037388442f6a2e435f4f30860a3",
         "region_id" : "region-abc-2",
         "enterprise_router_id" : "58fad9c1-b4bd-4622-84e4-a0fcb2423601",
         "enterprise_router_table_id" : "a5347056-e29f-4192-9256-e151c61f854c"
       } ]
     }, {
       "operation_id" : "CreateCentralNetworkErTable",
       "central_network_plane_name" : "default-plane",
       "create_central_network_er_table" : {
         "project_id" : "XXX",
         "region_id" : "region-abc",
         "enterprise_router_id" : "c73b26b7-33f0-438d-b440-8e87dfe6fef9",
         "enterprise_router_table_id" : "c0d51f20-0313-40f7-a74e-9dccb5da21c0"
       }
     }, {
       "operation_id" : "DeleteCentralNetworkErTable",
       "central_network_plane_name" : "default-plane",
       "delete_central_network_er_table" : {
         "project_id" : "XXX",
         "region_id" : "region-abc",
         "enterprise_router_id" : "395b0884-aab4-4bf0-8cb8-7f2da26708dd",
         "enterprise_router_table_id" : "cc542128-5c2d-402a-8960-53bb2ed9484e"
       }
     }, {
       "operation_id" : "SwitchCentralNetworkErTable",
       "central_network_plane_name" : "default-plane",
       "switch_central_network_er_table" : {
         "project_id" : "XXX",
         "region_id" : "region-abc",
         "enterprise_router_id" : "5cc75ed0-bd6c-3af4-663b-caba3315bb08",
         "original_enterprise_router_table_id" : "b705f49e-df88-eaf3-3aeb-95d534138156",
         "new_enterprise_router_table_id" : "b705f49e-df88-eaf3-3aeb-95d534138158"
       }
     } ]
   }

Status Codes
------------

=========== ============================================
Status Code Description
=========== ============================================
202         The central network policy has been applied.
=========== ============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
