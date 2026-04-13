:original_name: DeleteCentralNetworkPolicy.html

.. _DeleteCentralNetworkPolicy:

Deleting a Central Network Policy
=================================

Function
--------

This API is used to delete a central network policy. An applied policy cannot be deleted.

URI
---

DELETE /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}

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

**Status code: 204**

.. table:: **Table 3** Response header parameters

   ============ ====== ===========
   Parameter    Type   Description
   ============ ====== ===========
   x-request-id String ``-``
   ============ ====== ===========

Example Requests
----------------

Deleting a central network policy

.. code-block:: text

   DELETE /v3/{domain_id}/gcn/central-network/{central_network_id}/policies/{policy_id}

Example Responses
-----------------

None

Status Codes
------------

=========== ============================================
Status Code Description
=========== ============================================
204         The central network policy has been deleted.
=========== ============================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
