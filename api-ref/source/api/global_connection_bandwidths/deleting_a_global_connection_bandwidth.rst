:original_name: DeleteGlobalConnectionBandwidth.html

.. _DeleteGlobalConnectionBandwidth:

Deleting a Global Connection Bandwidth
======================================

Function
--------

This API is used to delete a global connection bandwidth.

URI
---

DELETE /v3/{domain_id}/gcb/gcbandwidths/{id}

.. table:: **Table 1** Path Parameters

   ========= ========= ====== ============
   Parameter Mandatory Type   Description
   ========= ========= ====== ============
   domain_id Yes       String Account ID.
   id        Yes       String Instance ID.
   ========= ========= ====== ============

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

**Status code: 204**

The global connection bandwidth has been deleted.

None

Example Requests
----------------

Deleting a global connection bandwidth

.. code-block:: text

   DELETE https://{cc_endpoint}/v3/{domain_id}/gcb/gcbandwidths/{id}

Example Responses
-----------------

None

Status Codes
------------

=========== =================================================
Status Code Description
=========== =================================================
204         The global connection bandwidth has been deleted.
=========== =================================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
