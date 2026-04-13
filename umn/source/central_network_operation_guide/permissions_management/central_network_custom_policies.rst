:original_name: cc_03_0992.html

.. _cc_03_0992:

Central Network Custom Policies
===============================

Custom policies can be created to supplement the system-defined policies.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Create a JSON policy or edit an existing one.

For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/permissions/creating_a_custom_policy.html>`__. The following section contains examples of common custom policies.

Example Custom Policies
-----------------------

-  Example 1: Allowing users to delete central networks

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "cc:centralNetwork:delete"
                  ]
              }
          ]
      }

-  Example 2: Denying the deletion of central network policies

   A policy with only "Deny" permissions must be used together with other policies. If the permissions granted to an IAM user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   The following method can be used if you need to assign permissions of the **CC FullAccess** policy to a user but also forbid the user from deleting central network policies. Create a custom policy and assign both policies to the group that the user belongs to. Then the user can perform all operations on Cloud Connect resources except deleting central network policies. The following is an example of a deny policy:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Deny",
                  "Action": [
                      "cc:centralNetwork:deletePolicy"
                  ]
              }
          ]
      }

-  Example 3: Create a custom policy containing multiple actions.

   A custom policy can contain the actions of multiple services that are of the global or project-level type. The following is an example policy containing actions of multiple services:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "cc:centralNetwork:create",
                      "cc:centralNetwork:update",
                      "cc:centralNetwork:delete",
                      "cc:centralNetwork:get"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "er:instances:create",
                      "er:instances:update",
                      "er:instances:delete",
                      "er:instances:get"
                  ]
              }
          ]
      }
