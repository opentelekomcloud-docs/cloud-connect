:original_name: ListCentralNetworkCapabilities.html

.. _ListCentralNetworkCapabilities:

Querying Central Network Capabilities
=====================================

Function
--------

This API is used to query central network capabilities.

URI
---

GET /v3/{domain_id}/gcn/capabilities

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
   | capability      | No              | Array of strings | Capabilities. Multiple capabilities can be queried.                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
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

   +--------------+--------------------------------------------------------------------------------------------------------------------------------+---------------------------------------+
   | Parameter    | Type                                                                                                                           | Description                           |
   +==============+================================================================================================================================+=======================================+
   | request_id   | String                                                                                                                         | Request ID.                           |
   +--------------+--------------------------------------------------------------------------------------------------------------------------------+---------------------------------------+
   | page_info    | :ref:`PageInfo <listcentralnetworkcapabilities__response_pageinfo>` object                                                     | Pagination query information.         |
   +--------------+--------------------------------------------------------------------------------------------------------------------------------+---------------------------------------+
   | capabilities | Array of :ref:`CentralNetworkCapabilityEntry <listcentralnetworkcapabilities__response_centralnetworkcapabilityentry>` objects | List of central network capabilities. |
   +--------------+--------------------------------------------------------------------------------------------------------------------------------+---------------------------------------+

.. _listcentralnetworkcapabilities__response_pageinfo:

.. table:: **Table 5** PageInfo

   =============== ======= ============================================
   Parameter       Type    Description
   =============== ======= ============================================
   next_marker     String  Backward pagination identifier.
   previous_marker String  Forward pagination identifier.
   current_count   Integer Number of the resources in the current list.
   =============== ======= ============================================

.. _listcentralnetworkcapabilities__response_centralnetworkcapabilityentry:

.. table:: **Table 6** CentralNetworkCapabilityEntry

   +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                                                                                   | Description                                                                                                                                  |
   +=======================+========================================================================================================================================+==============================================================================================================================================+
   | id                    | String                                                                                                                                 | Instance ID.                                                                                                                                 |
   +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
   | domain_id             | String                                                                                                                                 | ID of the account that the instance belongs to.                                                                                              |
   +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
   | capability            | String                                                                                                                                 | Central network capabilities.                                                                                                                |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **central-network.is-support**: central networks                                                                                          |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **central-network.is-support-enterprise-project**: enterprise projects for central networks                                               |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **central-network.is-support-tag**: central network tagging                                                                               |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **central-network.is-support-custom-er-table**: custom route tables on central networks                                                   |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **connection-bandwidth.size-range**: bandwidth capacity for a cross-site connection                                                       |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **connection-bandwidth.charge-mode**: billing mode of the global connection bandwidth for assigning cross-site connection bandwidths      |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **connection-bandwidth.free-line**: free lines for cross-site connections                                                                 |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-instance.support-regions**: list of the regions where Enterprise Router is available                                                 |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-instance.support-ipv6-regions**: list of the regions where Enterprise Router supports IPv6                                           |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-instance.support-dscp-regions**: list of the regions that support global connection bandwidth classes for enterprise routers         |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-instance.support-sts5-regions**: list of the regions where sts5 can make API calls to Enterprise Router                              |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-instance.support-sites**: list of the sites where Enterprise Router is available                                                     |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **custom-connections.is-support**: custom connections                                                                                     |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **custom-connections.support-regions**: list of the regions where custom connections can be created                                       |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **gdgw-instance.support-dscp-regions**: list of the regions where the bandwidth for global DC gateways has different classes              |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **gdgw-instance.support-freeze-regions**: list of the regions where global connection bandwidths used by global DC gateways can be frozen |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **gdgw-attachment.is-support**: global DC gateways as attachments                                                                         |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **gdgw-attachment.support-regions**: list of the regions where global DC gateways can be used as attachments                              |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **gdgw-attachment.support-sites**: list of the sites where global DC gateways can be used as attachments                                  |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-route-table-attachment.is-support**: enterprise router route tables as attachments                                                   |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-route-table-attachment.support-regions**: list of the regions where enterprise router route tables can be used as attachments        |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **er-route-table-attachment.support-sites**: list of the sites where enterprise router route tables can be used as attachments            |
   |                       |                                                                                                                                        |                                                                                                                                              |
   |                       |                                                                                                                                        | -  **cloud-alliance.support-regions**: list of the regions that support Cloud Alliance                                                       |
   +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
   | specifications        | :ref:`CentralNetworkCapabilitySpecifications <listcentralnetworkcapabilities__response_centralnetworkcapabilityspecifications>` object | Central network specification details.                                                                                                       |
   +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+

.. _listcentralnetworkcapabilities__response_centralnetworkcapabilityspecifications:

.. table:: **Table 7** CentralNetworkCapabilitySpecifications

   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | Parameter              | Type                                                                                                                       | Description                                           |
   +========================+============================================================================================================================+=======================================================+
   | is_support             | Boolean                                                                                                                    | Whether central network specifications are supported. |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | size_range             | :ref:`ConnectionBandwidthSizeRange <listcentralnetworkcapabilities__response_connectionbandwidthsizerange>` object         | JSON                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | charge_mode            | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | free_lines             | Array of :ref:`ConnectionBandwidthFreeLine <listcentralnetworkcapabilities__response_connectionbandwidthfreeline>` objects | List of free lines.                                   |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_regions        | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_ipv6_regions   | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_dscp_regions   | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_sts5_regions   | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_sites          | Array of :ref:`SiteSpecifications <listcentralnetworkcapabilities__response_sitespecifications>` objects                   | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
   | support_freeze_regions | Array of strings                                                                                                           | List                                                  |
   +------------------------+----------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+

.. _listcentralnetworkcapabilities__response_connectionbandwidthsizerange:

.. table:: **Table 8** ConnectionBandwidthSizeRange

   ========= ==== ==============
   Parameter Type Description
   ========= ==== ==============
   min       Long Minimum value.
   max       Long Maximum value.
   ========= ==== ==============

.. _listcentralnetworkcapabilities__response_connectionbandwidthfreeline:

.. table:: **Table 9** ConnectionBandwidthFreeLine

   ========= ================ ===========
   Parameter Type             Description
   ========= ================ ===========
   [items]   Array of strings Free line.
   ========= ================ ===========

.. _listcentralnetworkcapabilities__response_sitespecifications:

.. table:: **Table 10** SiteSpecifications

   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                                          |
   +===========+========+======================================================================================================================+
   | region_id | String | Region ID.                                                                                                           |
   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+
   | site_code | String | Site code. You can obtain the code by calling the API for querying the site list of the global connection bandwidth. |
   +-----------+--------+----------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Querying central network capabilities

.. code-block:: text

   GET https://{cc_endpoint}/v3/{domain_id}/gcn/capabilities

Example Responses
-----------------

**Status code: 200**

Central network capabilities have been queried.

.. code-block::

   {
     "request_id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
     "page_info" : {
       "current_count" : 1
     },
     "capabilities" : [ {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "central-network.is-support",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "central-network.is-support-tag",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-route-table-attachment.is-support",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "central-network.is-support-custom-er-table",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "central-network.is-support-enterprise-project",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "gdgw-attachment.is-support",
       "specifications" : {
         "is_support" : true
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "gdgw-attachment.support-regions",
       "specifications" : {
         "support_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-instance.support-sts5-regions",
       "specifications" : {
         "support_sts5_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-route-table-attachment.support-sites",
       "specifications" : {
         "support_sites" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-instance.support-regions",
       "specifications" : {
         "support_regions" : [ "region1", "region2" ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "connection-bandwidth.charge-mode",
       "specifications" : {
         "charge_mode" : [ "bwd" ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "gdgw-instance.support-freeze-regions",
       "specifications" : {
         "support_freeze_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "connection-bandwidth.size-range",
       "specifications" : {
         "size_range" : {
           "min" : 1,
           "max" : 2
         }
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "gdgw-instance.support-dscp-regions",
       "specifications" : {
         "support_dscp_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-instance.support-ipv6-regions",
       "specifications" : {
         "support_ipv6_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "cloud-alliance.support-regions",
       "specifications" : {
         "support_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "gdgw-attachment.support-sites",
       "specifications" : {
         "support_sites" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-instance.support-dscp-regions",
       "specifications" : {
         "support_dscp_regions" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-instance.support-sites",
       "specifications" : {
         "support_sites" : [ ]
       }
     }, {
       "id" : "a3bad420-33b8-4e26-9e9b-bdf67aa8e72b",
       "domain_id" : "XXX",
       "capability" : "er-route-table-attachment.support-regions",
       "specifications" : {
         "support_regions" : [ ]
       }
     } ]
   }

Status Codes
------------

=========== ===============================================
Status Code Description
=========== ===============================================
200         Central network capabilities have been queried.
=========== ===============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
