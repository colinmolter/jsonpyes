json-py-es
==========

Alexander Liu \* To import raw JSON data files to ElasticSearch using
Python in one line of commands

Installation
~~~~~~~~~~~~

-  ``pip install jsonpyes``

    In the past we import data in this way. Too many jobs by hands...
    |Alt|

    Using ElasticSearch Bulk API to import this data, sometimes ES only
    recognizes data in its API way.

    But now let ``json-py-es`` glue them all.

jsonpyes
--------

.. figure:: static/snapshot139.png
   :alt: Alt

   Alt
Instructions:
^^^^^^^^^^^^^

::

    There are 3 proccesses of importing raw JSON data to ElasticSearch
    1. Only validating raw JSON data
    2. Without validating ,just import data to ElasticSearch
    3. After validating successfully, then import data to ElasticSearch

1. Only validating
''''''''''''''''''

-  ``jsonpyes --data raw_data.json --check``

-  If the json data file is valid: |Alt|

-  If the json data file is invalid: |Alt|

2. Only importing without validating
''''''''''''''''''''''''''''''''''''

-  Notice: If the raw JSON data file is invalid, ElasticSearch will not
   import it.
-  ``jsonpyes --data raw_data.json --bulk http://localhost:9200 --import --index myindex2 --type mytype2``
-  Or enable multi-threads
   ``jsonpyes --data raw_data.json --bulk http://localhost:9200 --import --index myindex2 --type mytype2 --thread 8``
   |Alt|

\*\* jsonpyes supports multi-threads when importing data to
elasticsearch |Alt|

    As you can see these two containers have same docs loaded, if we use
    ***--thread 8*** it could be slightly faster. That really depends on
    your computer/server resources. This was tested on a 4GB RAM /
    2.4Ghz intel i5 Linux x64 laptop system.

.. figure:: static/snapshot133.png
   :alt: Alt

   Alt

-  And it works. |Alt|

3. Both validating and importing
''''''''''''''''''''''''''''''''

-  ``jsonpyes --data raw_data.json --bulk http://localhost:9200 --import --index myindex1 --type mytype1 --check``
   |Alt|

-  And it works. |Alt|

Happy hacking!
''''''''''''''

.. |Alt| image:: static/snapshot106.jpg
.. |Alt| image:: static/snapshot98.jpg
.. |Alt| image:: static/snapshot99.jpg
.. |Alt| image:: static/snapshot102.jpg
.. |Alt| image:: static/snapshot132.png
.. |Alt| image:: static/snapshot105.jpg
.. |Alt| image:: static/snapshot135.png
.. |Alt| image:: static/snapshot101.jpg