:original_name: cc_03_0884.html

.. _cc_03_0884:

Central Network Metrics
=======================

Description
-----------

By setting up a central network, you can enable communication between enterprise routers, as well as between enterprise routers and your on-premises data center, in the same region or across regions. When a central network is used, attachments on the enterprise routers used in the central network policy will be monitored.

This section describes metrics reported by enterprise routers in the central network policy to Cloud Eye as well as their namespaces and dimensions. You can view the metrics on the Cloud Eye console.

Namespace
---------

SYS.ER

Metrics
-------

.. table:: **Table 1** Monitoring metrics of an attachment

   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | ID                                | Name                                    | Description                                                                             | Value Range | Unit  | Conversion Rule | Monitored Object (Dimension)    | Monitoring Interval (Raw Data) |
   +===================================+=========================================+=========================================================================================+=============+=======+=================+=================================+================================+
   | attachment_bytes_in               | Inbound Traffic                         | Network traffic going into the attachment                                               | >= 0        | Byte  | 1024 (IEC)      | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bytes_out              | Outbound Traffic                        | Network traffic going out of the attachment                                             | >= 0        | Byte  | 1024 (IEC)      | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bits_rate_in           | Inbound Bandwidth                       | Network traffic per second going into the attachment                                    | >= 0        | bit/s | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_bits_rate_out          | Outbound Bandwidth                      | Network traffic per second going out of the attachment                                  | >= 0        | bit/s | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_in             | Inbound PPS                             | Packets per second going into the attachment                                            | >= 0        | PPS   | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_out            | Outbound PPS                            | Packets per second going out of the attachment                                          | >= 0        | PPS   | 1000 (SI)       | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_drop_blackhole | Packets Dropped by Black Hole Route     | The number of packets dropped because they matched a black hole route on the attachment | >= 0        | Count | N/A             | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+
   | attachment_packets_drop_noroute   | Packets Dropped Due to No Route Matched | The number of packets dropped because they did not match a route on the attachment      | >= 0        | Count | N/A             | er_instance_id,er_attachment_id | 1 minute                       |
   +-----------------------------------+-----------------------------------------+-----------------------------------------------------------------------------------------+-------------+-------+-----------------+---------------------------------+--------------------------------+

Dimensions
----------

================ ============================
Key              Value
================ ============================
er_attachment_id Enterprise router attachment
================ ============================
