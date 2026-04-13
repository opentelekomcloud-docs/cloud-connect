:original_name: ListGlobalConnectionBandwidthConfigs.html

.. _ListGlobalConnectionBandwidthConfigs:

Querying the Tenant Configuration of a Global Connection Bandwidth
==================================================================

Function
--------

This API is used to query the tenant configuration of a global connection bandwidth.

URI
---

GET /v3/{domain_id}/gcb/configs

.. table:: **Table 1** Path Parameters

   ========= ========= ====== ===========
   Parameter Mandatory Type   Description
   ========= ========= ====== ===========
   domain_id Yes       String Account ID.
   ========= ========= ====== ===========

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

   +------------+------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
   | Parameter  | Type                                                                                                                                     | Description                                                               |
   +============+==========================================================================================================================================+===========================================================================+
   | request_id | String                                                                                                                                   | Request ID.                                                               |
   +------------+------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
   | configs    | :ref:`ListGlobalConnectionBandwidthConfigs <listglobalconnectionbandwidthconfigs__response_listglobalconnectionbandwidthconfigs>` object | Dynamic configuration items for purchasing a global connection bandwidth. |
   +------------+------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+

.. _listglobalconnectionbandwidthconfigs__response_listglobalconnectionbandwidthconfigs:

.. table:: **Table 4** ListGlobalConnectionBandwidthConfigs

   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                                                                                           | Description                                                                                         |
   +=======================+================================================================================================================================================+=====================================================================================================+
   | size_range            | Array of :ref:`GlobalConnectionBandwidthSizeRange <listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthsizerange>` objects | Capacity of global connection bandwidths by billing option.                                         |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | charge_mode           | Array of strings                                                                                                                               | List of supported billing options.                                                                  |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | services              | Array of strings                                                                                                                               | Instance type.                                                                                      |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | gcb_type              | Array of strings                                                                                                                               | Bandwidth type.                                                                                     |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | ratio_95peak_plus     | Integer                                                                                                                                        | Percentage of the minimum bandwidth in enhanced 95th percentile bandwidth billing.                  |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | ratio_95peak_guar     | Integer                                                                                                                                        | Percentage of the minimum bandwidth in standard 95th percentile bandwidth billing.                  |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | crossborder           | Boolean                                                                                                                                        | Whether a cross-border permit is approved.                                                          |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | quotas                | Array of :ref:`GlobalConnectionBandwidthQuotas <listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthquotas>` objects       | Quota information.                                                                                  |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | sla_level             | Array of strings                                                                                                                               | Line grade.                                                                                         |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | bind_limit            | Integer                                                                                                                                        | Maximum number of instances that are allowed to use a shared bandwidth.                             |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | enable_area_bandwidth | Boolean                                                                                                                                        | Whether to enable the geographic region bandwidth.                                                  |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | enable_change_95      | Boolean                                                                                                                                        | Whether standard 95th percentile bandwidth billing can be changed to billing by bandwidth capacity. |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | enable_spec_code      | Boolean                                                                                                                                        | Whether multiple line specifications are supported.                                                 |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | ces_enabled           | Boolean                                                                                                                                        | Whether to enable Cloud Eye monitoring.                                                             |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | gcbType               | Array of strings                                                                                                                               | Bandwidth type.                                                                                     |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | gcbSizeRange          | Array of :ref:`GlobalConnectionBandwidthSizeRange <listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthsizerange>` objects | Bandwidth range of global connection bandwidths by billing option.                                  |
   |                       |                                                                                                                                                |                                                                                                     |
   |                       |                                                                                                                                                | This parameter has been discarded. Please do not use it.                                            |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | relation              | :ref:`GlobalConnectionBandwidthRelation <listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthrelation>` object             | Instance type.                                                                                      |
   |                       |                                                                                                                                                |                                                                                                     |
   |                       |                                                                                                                                                | This parameter has been discarded. Please do not use it.                                            |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+
   | chargeMode            | Array of strings                                                                                                                               | List of supported billing options.                                                                  |
   |                       |                                                                                                                                                |                                                                                                     |
   |                       |                                                                                                                                                | This parameter has been discarded. Please do not use it.                                            |
   +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------+

.. _listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthquotas:

.. table:: **Table 5** GlobalConnectionBandwidthQuotas

   +-----------------------+-----------------------+----------------------------------------------------------+
   | Parameter             | Type                  | Description                                              |
   +=======================+=======================+==========================================================+
   | quota                 | Integer               | Quotas.                                                  |
   +-----------------------+-----------------------+----------------------------------------------------------+
   | used                  | Integer               | Used quotas.                                             |
   +-----------------------+-----------------------+----------------------------------------------------------+
   | type                  | String                | Quota type.                                              |
   |                       |                       |                                                          |
   |                       |                       | -  **gcb.size**: global connection bandwidth capacity    |
   |                       |                       |                                                          |
   |                       |                       | -  **gcb.count**: number of global connection bandwidths |
   +-----------------------+-----------------------+----------------------------------------------------------+

.. _listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthsizerange:

.. table:: **Table 6** GlobalConnectionBandwidthSizeRange

   +-----------------------+-----------------------+-------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                   |
   +=======================+=======================+===============================================================================+
   | type                  | String                | Billing option.                                                               |
   |                       |                       |                                                                               |
   |                       |                       | Range:                                                                        |
   |                       |                       |                                                                               |
   |                       |                       | -  **bwd**: billing by bandwidth                                              |
   |                       |                       |                                                                               |
   |                       |                       | -  **95**: standard 95th percentile bandwidth billing (not supported)         |
   |                       |                       |                                                                               |
   |                       |                       | -  **95avr**: average daily 95th percentile bandwidth billing (not supported) |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------+
   | min                   | Integer               | Minimum global connection bandwidth, in Mbit/s.                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------+
   | max                   | Integer               | Maximum global connection bandwidth, in Mbit/s.                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------+

.. _listglobalconnectionbandwidthconfigs__response_globalconnectionbandwidthrelation:

.. table:: **Table 7** GlobalConnectionBandwidthRelation

   ========= ================ ==============
   Parameter Type             Description
   ========= ================ ==============
   Area      Array of strings Instance type.
   ========= ================ ==============

Example Requests
----------------

Querying the tenant configuration of a global connection bandwidth

.. code-block:: text

   GET https://{cc_endpoint}/v3/{domain_id}/gcb/configs

Example Responses
-----------------

**Status code: 200**

The tenant configuration of the global connection bandwidth has been queried.

.. code-block::

   {
     "request_id" : "61126320a1802d5c6444f9d2d76526c2",
     "configs" : {
       "size_range" : [ {
         "min" : 2,
         "max" : 300,
         "type" : "bwd"
       } ],
       "charge_mode" : [ "bwd", 95, "95avr" ],
       "services" : [ "GEIP", "CC", "GCN", "GSN" ],
       "gcb_type" : [ "Region", "SubArea", "Area", "TrsArea" ],
       "ratio_95peak_guar" : 0,
       "crossborder" : false,
       "quotas" : [ {
         "quota" : 99999999,
         "used" : 3451,
         "type" : "gcb.size"
       }, {
         "quota" : 10000,
         "used" : 16,
         "type" : "gcb.count"
       } ],
       "bind_limit" : 200,
       "sla_level" : [ "Pt", "Au", "Ag" ]
     }
   }

Status Codes
------------

+-------------+-------------------------------------------------------------------------------+
| Status Code | Description                                                                   |
+=============+===============================================================================+
| 200         | The tenant configuration of the global connection bandwidth has been queried. |
+-------------+-------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
