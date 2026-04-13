:original_name: ListCentralNetworkPolicyChangeSet.html

.. _ListCentralNetworkPolicyChangeSet:

Querying the Changes Between the Current Policy and an Applied Policy
=====================================================================

Function
--------

This API is used query the changes between the current policy and an applied policy.

URI
---

GET /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/change-set

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

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | Parameter                         | Type                                                                                                                                    | Description                             |
   +===================================+=========================================================================================================================================+=========================================+
   | request_id                        | String                                                                                                                                  | Request ID.                             |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | page_info                         | :ref:`PageInfo <listcentralnetworkpolicychangeset__response_pageinfo>` object                                                           | Pagination query information.           |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+
   | central_network_policy_change_set | Array of :ref:`CentralNetworkElementChangeEntry <listcentralnetworkpolicychangeset__response_centralnetworkelementchangeentry>` objects | List of central network policy changes. |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------+

.. _listcentralnetworkpolicychangeset__response_pageinfo:

.. table:: **Table 4** PageInfo

   =============== ======= ============================================
   Parameter       Type    Description
   =============== ======= ============================================
   next_marker     String  Backward pagination identifier.
   previous_marker String  Forward pagination identifier.
   current_count   Integer Number of the resources in the current list.
   =============== ======= ============================================

.. _listcentralnetworkpolicychangeset__response_centralnetworkelementchangeentry:

.. table:: **Table 5** CentralNetworkElementChangeEntry

   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Parameter                            | Type                                                                                                                            | Description                                                                                                      |
   +======================================+=================================================================================================================================+==================================================================================================================+
   | operation_id                         | String                                                                                                                          | Instance status.                                                                                                 |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **CreateCentralNetworkPlane**: adds a central network plane.                                                  |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **DeleteCentralNetworkPlane**: removes a central network plane.                                               |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **UpdateCentralNetworkPlane**: updates a central network plane.                                               |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **CreateCentralNetworkErInstance**: adds an enterprise router as an attachment on a central network.          |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **DeleteCentralNetworkErInstance**: removes an enterprise router from a central network.                      |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **CreateCentralNetworkErConnection**: creates a connection between enterprise routers on a central network.   |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **DeleteCentralNetworkErConnection**: deletes a connection between enterprise routers from a central network. |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **CreateCentralNetworkErTable**: adds an enterprise router route table as an attachment on a central network. |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **DeleteCentralNetworkErTable**: removes an enterprise router route table from a central network.             |
   |                                      |                                                                                                                                 |                                                                                                                  |
   |                                      |                                                                                                                                 | -  **SwitchCentralNetworkErTable**: changes an enterprise router route table on a central network.               |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <listcentralnetworkpolicychangeset__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | original_central_network_plane       | :ref:`CentralNetworkPlaneChangeDocument <listcentralnetworkpolicychangeset__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | newest_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <listcentralnetworkpolicychangeset__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_plane         | :ref:`CentralNetworkPlaneChangeDocument <listcentralnetworkpolicychangeset__response_centralnetworkplanechangedocument>` object | Central network plane document.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_instance   | :ref:`AssociateErInstanceDocument <listcentralnetworkpolicychangeset__response_associateerinstancedocument>` object             | Details of the central network.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_instance   | :ref:`AssociateErInstanceDocument <listcentralnetworkpolicychangeset__response_associateerinstancedocument>` object             | Details of the central network.                                                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | central_network_plane_name           | String                                                                                                                          | Name of the central network plane.                                                                               |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_connection | Array of :ref:`AssociateErTableDocument <listcentralnetworkpolicychangeset__response_associateertabledocument>` objects         | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_connection | Array of :ref:`AssociateErTableDocument <listcentralnetworkpolicychangeset__response_associateertabledocument>` objects         | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | create_central_network_er_table      | :ref:`AssociateErTableDocument <listcentralnetworkpolicychangeset__response_associateertabledocument>` object                   | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | delete_central_network_er_table      | :ref:`AssociateErTableDocument <listcentralnetworkpolicychangeset__response_associateertabledocument>` object                   | Enterprise router route table associated with the central network plane.                                         |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | switch_central_network_er_table      | :ref:`SwitchErTableDocument <listcentralnetworkpolicychangeset__response_switchertabledocument>` object                         | Policy document for changing the enterprise router route table.                                                  |
   +--------------------------------------+---------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+

.. _listcentralnetworkpolicychangeset__response_centralnetworkplanechangedocument:

.. table:: **Table 6** CentralNetworkPlaneChangeDocument

   +------------------------+-------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | Parameter              | Type                                                                                                                          | Description                                                                    |
   +========================+===============================================================================================================================+================================================================================+
   | name                   | String                                                                                                                        | Instance name.                                                                 |
   +------------------------+-------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | is_default             | Boolean                                                                                                                       | Whether the plane is the default one.                                          |
   +------------------------+-------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | associate_er_tables    | Array of :ref:`AssociateErTableDocument <listcentralnetworkpolicychangeset__response_associateertabledocument>` objects       | List of the enterprise routers on a central network.                           |
   +------------------------+-------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+
   | exclude_er_connections | Array of :ref:`ExcludeErConnectionDocument <listcentralnetworkpolicychangeset__response_excludeerconnectiondocument>` objects | Whether to exclude the connections to enterprise routers on a central network. |
   +------------------------+-------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------+

.. _listcentralnetworkpolicychangeset__response_excludeerconnectiondocument:

.. table:: **Table 7** ExcludeErConnectionDocument

   +-----------+-------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+
   | Parameter | Type                                                                                                                          | Description                                                                  |
   +===========+===============================================================================================================================+==============================================================================+
   | [items]   | Array of :ref:`AssociateErInstanceDocument <listcentralnetworkpolicychangeset__response_associateerinstancedocument>` objects | Connections between enterprise routers managed by the central network plane. |
   +-----------+-------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------+

.. _listcentralnetworkpolicychangeset__response_associateerinstancedocument:

.. table:: **Table 8** AssociateErInstanceDocument

   ==================== ====== =====================
   Parameter            Type   Description
   ==================== ====== =====================
   enterprise_router_id String Enterprise router ID.
   project_id           String Project ID.
   region_id            String Region ID.
   ==================== ====== =====================

.. _listcentralnetworkpolicychangeset__response_associateertabledocument:

.. table:: **Table 9** AssociateErTableDocument

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

.. _listcentralnetworkpolicychangeset__response_switchertabledocument:

.. table:: **Table 10** SwitchErTableDocument

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

Querying the changes between the current policy and an applied policy

.. code-block:: text

   GET /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}/change-set

Example Responses
-----------------

**Status code: 200**

Changes between the current policy and applied policy have been queried.

.. code-block::

   {
     "request_id" : "a334adc3e2cba87855de6f3ab58b9db5",
     "page_info" : {
       "current_count" : 5
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

+-------------+--------------------------------------------------------------------------+
| Status Code | Description                                                              |
+=============+==========================================================================+
| 200         | Changes between the current policy and applied policy have been queried. |
+-------------+--------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
