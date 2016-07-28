.. title:: pysnow

pysnow
======

Python library for the ServiceNow REST API focused on ease of use and elegant syntax.

The REST API is active by default in all instances, starting with the Eureka release.
Compatible with both Python 2 and 3. Tested with 2.7 and 3.4.

Getting started
---------------
pip install pysnow


Basic usage
-----------

.. code-block:: python

   import pysnow

   # Create client object
   s = pysnow.Client(instance='myinstance',
		     user='myusername',
		     password='mypassword',
		     raise_on_empty=True)

   # Create a new record
   s.insert(table='incident', {'field1': 'value1', 'field2': 'value2'})

   # Create a `Request` object by querying for 'INC01234' on table 'incident'
   r = s.query(table='incident', query={'number': 'INC01234'})

   # Fetch one record and filter out everything but 'number' and 'sys_id' from the results
   res = r.get_one(fields=['number', 'sys_id'])

   # Update
   r.update({'this': 'that'})

   # Delete
   r.delete()


See the `documentation <http://pysnow.readthedocs.org/>`_. for more examples and other info

Quick links
-----------

* http://wiki.servicenow.com/index.php?title=REST_API
* http://wiki.servicenow.com/index.php?title=Table_API
* http://wiki.servicenow.com/index.php?title=Tables_and_Classes
* http://wiki.servicenow.com/index.php?title=Encoded_Query_Strings


