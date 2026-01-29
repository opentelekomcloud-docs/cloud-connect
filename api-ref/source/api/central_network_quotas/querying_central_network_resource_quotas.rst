:original_name: ListCentralNetworkQuotas.html

.. _ListCentralNetworkQuotas:

Querying Central Network Resource Quotas
========================================

Function
--------

This API is used to query the resource quotas.

URI
---

GET /v3/{domain_id}/gcn/quotas

.. table:: **Table 1** Path Parameters

   ========= ========= ====== ===========
   Parameter Mandatory Type   Description
   ========= ========= ====== ===========
   domain_id Yes       String Account ID.
   ========= ========= ====== ===========

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
   +=================+=================+==================+=======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | quota_type      | No              | Array of strings | Quota type. Multiple quota types can be queried.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | No              | Integer          | Number of records returned on each page.                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |                 |                 |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
   |                 |                 |                  | The value ranges from 1 to 2000.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | marker          | No              | String           | Pagination query information. You can obtain the **marker** values from the response of the last API call. You can enter the **marker** value of the previous page or the next page. If you enter the **marker** value of the previous page, the previous page will be queried. If you enter the **marker** value of the next page, the next page will be queried. During pagination query, the query criteria, including the filters, sorting criteria, and the **limit** value, cannot be modified. |
   +-----------------+-----------------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   ============ ========= ====== ===========
   Parameter    Mandatory Type   Description
   ============ ========= ====== ===========
   X-Auth-Token No        String User token.
   ============ ========= ====== ===========

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +------------+------------------------------------------------------------------------------------------------------+-------------+
   | Parameter  | Type                                                                                                 | Description |
   +============+======================================================================================================+=============+
   | request_id | String                                                                                               | Request ID. |
   +------------+------------------------------------------------------------------------------------------------------+-------------+
   | quotas     | Array of :ref:`CentralNetworkQuota <listcentralnetworkquotas__response_centralnetworkquota>` objects | Quota list. |
   +------------+------------------------------------------------------------------------------------------------------+-------------+

.. _listcentralnetworkquotas__response_centralnetworkquota:

.. table:: **Table 5** CentralNetworkQuota

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                  |
   +=======================+=======================+==============================================================================================================================================================+
   | quota_key             | String                | Quota type of a central network.                                                                                                                             |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **central_networks_per_account**: number of central networks per account                                                                                  |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **policy_versions_per_central_network**: number of policies per central network                                                                           |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **size_of_document_per_central_network_policy_version**: size of the central network policy document, in KB                                               |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **planes_per_central_network**: number of planes per central network                                                                                      |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **er_instances_per_region_per_central_network**: number of enterprise routers that can be added to each central network as attachments in each region     |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **connections_per_central_network**: number of connections per central network                                                                            |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **attachments_per_central_network**: number of attachments per central network                                                                            |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **GDGW_attachments_per_region_per_central_network**: number of global DC gateways that can be added to each central network as attachments in each region |
   |                       |                       |                                                                                                                                                              |
   |                       |                       | -  **ER_ROUTE_TABLE_attachments_per_region_per_central_network**: number of enterprise router route table attachments on each central network in each region |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | quota_limit           | Integer               | Quotas.                                                                                                                                                      |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | used                  | Integer               | Used quotas.                                                                                                                                                 |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | unit                  | String                | Unit of the quota value.                                                                                                                                     |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Querying resource quotas

.. code-block:: text

   GET https://{cc_endpoint}/v3/{domain_id}/gcn/quotas

Example Responses
-----------------

**Status code: 200**

The central network resource quotas have been queried.

.. code-block::

   {
     "request_id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
     "quotas" : [ {
       "quota_key" : "central_networks_per_account",
       "quota_limit" : 6,
       "used" : 0,
       "unit" : "count"
     }, {
       "quota_key" : "policy_versions_per_central_network",
       "quota_limit" : 500,
       "unit" : "count"
     }, {
       "quota_key" : "er_instances_per_region_per_central_network",
       "quota_limit" : 1,
       "unit" : "count"
     }, {
       "quota_key" : "connections_per_central_network",
       "quota_limit" : -1,
       "unit" : "count"
     }, {
       "quota_key" : "GDGW_attachments_per_region_per_central_network",
       "quota_limit" : 3,
       "unit" : "count"
     }, {
       "quota_key" : "ER_ROUTE_TABLE_attachments_per_region_per_central_network",
       "quota_limit" : 3,
       "unit" : "count"
     }, {
       "quota_key" : "attachments_per_central_network",
       "quota_limit" : -1,
       "unit" : "count"
     }, {
       "quota_key" : "size_of_document_per_central_network_policy_version",
       "quota_limit" : 10240,
       "unit" : "KB"
     } ]
   }

Status Codes
------------

=========== ======================================================
Status Code Description
=========== ======================================================
200         The central network resource quotas have been queried.
=========== ======================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
