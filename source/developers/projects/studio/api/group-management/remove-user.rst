.. include:: /includes/unicode-checkmark.rst

.. _crafter-studio-api-group-remove-user:

======================
Remove User from Group
======================

Remove a user from a Crafter Studio group.

--------------------
Resource Information
--------------------

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || POST                                                             |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/services/api/1/group/remove-user.json``                 |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+
|| Required Role             || Admin                                                            |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

+---------------+-------------+---------------+--------------------------------------------------+
|| Name         || Type       || Required     || Description                                     |
+===============+=============+===============+==================================================+
|| username     || String     || |checkmark|  || Username to use                                 |
+---------------+-------------+---------------+--------------------------------------------------+
|| group_name   || String     || |checkmark|  || Group name to use                               |
+---------------+-------------+---------------+--------------------------------------------------+
|| site_id      || String     || |checkmark|  || Parent site ID                                  |
+---------------+-------------+---------------+--------------------------------------------------+

-------
Example
-------

.. code-block:: json

	POST .../api/1/services/api/1/group/remove-user.json

.. code-block:: json

  {
    "username" : "jane.doe",
    "group_name" : "contributors",
    "site_id" : "mysite"
  }

--------
Response
--------

+---------+-----------------------------------------------+----------------------------------------------+
|| Status || Location                                     || Response Body                               |
+=========+===============================================+==============================================+
|| 204    ||                                              ||                                             |
+---------+-----------------------------------------------+----------------------------------------------+
|| 401    ||                                              || ``{ "message" : "Unauthorized" }``          |
+---------+-----------------------------------------------+----------------------------------------------+
|| 404    ||                                              || ``{ "message" : "Group/user not found" }``  |
||        ||                                              ||                                             |
||        ||                                              || *Status message will indicate which entity* |
||        ||                                              || *is not found.*                             |
+---------+-----------------------------------------------+----------------------------------------------+
|| 500    ||                                              || ``{ "message" : "Internal server error" }`` |
+---------+-----------------------------------------------+----------------------------------------------+
