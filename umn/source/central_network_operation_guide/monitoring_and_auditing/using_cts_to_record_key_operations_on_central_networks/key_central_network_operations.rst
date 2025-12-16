:original_name: gcn_sj_0001.html

.. _gcn_sj_0001:

Key Central Network Operations
==============================

Scenarios
---------

With CTS, you can record operations associated with central networks and global connection bandwidths for later query, audit, and backtracking.

Prerequisites
-------------

You have enabled CTS.

Key Operations Recorded by CTS
------------------------------

.. table:: **Table 1** Central network operations that can be recorded by CTS

   +---------------------------------------+--------------------------+--------------------------------+
   | Operation                             | Resource                 | Trace                          |
   +=======================================+==========================+================================+
   | Creating a central network            | centralNetwork           | createCentralNetwork           |
   +---------------------------------------+--------------------------+--------------------------------+
   | Updating a central network            | centralNetwork           | updateCentralNetwork           |
   +---------------------------------------+--------------------------+--------------------------------+
   | Deleting a central network            | centralNetwork           | deleteCentralNetwork           |
   +---------------------------------------+--------------------------+--------------------------------+
   | Adding a central network policy       | centralNetworkPolicy     | createCentralNetworkPolicy     |
   +---------------------------------------+--------------------------+--------------------------------+
   | Applying a central network policy     | centralNetworkPolicy     | applyCentralNetworkPolicy      |
   +---------------------------------------+--------------------------+--------------------------------+
   | Deleting a central network policy     | centralNetworkPolicy     | deleteCentralNetworkPolicy     |
   +---------------------------------------+--------------------------+--------------------------------+
   | Updating a central network connection | centralNetworkConnection | updateCentralNetworkConnection |
   +---------------------------------------+--------------------------+--------------------------------+

.. table:: **Table 2** Global connection bandwidth operations recorded by CTS

   +----------------------------------------------------------+---------------------------+-------------------+
   | Operation                                                | Resource                  | Trace             |
   +==========================================================+===========================+===================+
   | Creating a global connection bandwidth                   | globalConnectionBandwidth | createGcBandwidth |
   +----------------------------------------------------------+---------------------------+-------------------+
   | Updating a global connection bandwidth                   | globalConnectionBandwidth | updateGcBandwidth |
   +----------------------------------------------------------+---------------------------+-------------------+
   | Deleting a global connection bandwidth                   | globalConnectionBandwidth | deleteGcBandwidth |
   +----------------------------------------------------------+---------------------------+-------------------+
   | Binding a global connection bandwidth to an instance     | globalConnectionBandwidth | bindGcBandwidth   |
   +----------------------------------------------------------+---------------------------+-------------------+
   | Unbinding a global connection bandwidth from an instance | globalConnectionBandwidth | unbindGcBandwidth |
   +----------------------------------------------------------+---------------------------+-------------------+
