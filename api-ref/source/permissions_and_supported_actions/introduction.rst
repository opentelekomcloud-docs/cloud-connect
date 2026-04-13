:original_name: cc_02_0002.html

.. _cc_02_0002:

Introduction
============

You can use Identity and Access Management (IAM) for fine-grained permissions management of your Cloud Connect resources. If your account does not need individual IAM users, you can skip this topic.

With IAM, you can control access to specific cloud resources. IAM supports role/policy-based authorization and identity policy-based authorization.

The following table describes the differences between the two authorization models.

.. table:: **Table 1** Differences between role/policy-based and identity policy-based authorization

   +---------------------+-------------------------------------+-------------------------------------+----------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Authorization Model | Authorization Using                 | Permissions                         | Authorization Method                         | Scenario                                                                                                                                                                                                                                                                                                                   |
   +=====================+=====================================+=====================================+==============================================+============================================================================================================================================================================================================================================================================================================================+
   | Role/Policy         | User-permission-authorization scope | -  System-defined roles             | Assigning roles or policies to principals    | To authorize a user, you need to add it to a user group first and then specify the scope of authorization. It is hard to provide fine-grained permissions control using authorization by user groups and a limited number of condition keys. This method is suitable for small- and medium-sized enterprises.              |
   |                     |                                     | -  System-defined policies          |                                              |                                                                                                                                                                                                                                                                                                                            |
   |                     |                                     | -  Custom policies                  |                                              |                                                                                                                                                                                                                                                                                                                            |
   +---------------------+-------------------------------------+-------------------------------------+----------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Identity policy     | User-policy                         | -  System-defined identity policies | -  Assigning identity policies to principals | You can authorize a user by attaching an identity policy to it. User-specific authorization and a variety of key conditions allow for more fine-grained permissions control. However, this model can be hard to set up. It requires a certain amount of expertise and is suitable for medium- and large-sized enterprises. |
   |                     |                                     | -  Custom identity policies         | -  Attaching identity policies to principals |                                                                                                                                                                                                                                                                                                                            |
   +---------------------+-------------------------------------+-------------------------------------+----------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Policies and actions in the two authorization models are not interoperable. You are advised to use the identity policy-based authorization model.

If you use IAM users in your account to call an API, the IAM users must be granted the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully.

Assume that an IAM user wants to call an API to query central networks. With role/policy-based authorization, the IAM user must be granted the permissions allowing for action **cc:centralNetwork:list**. With identity policy-based authorization, the IAM user must be granted the permissions allowing for action **cc:centralNetwork:list**.
