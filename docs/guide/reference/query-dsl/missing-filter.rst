.. _es-guide-reference-query-dsl-missing-filter:

==============
Missing Filter
==============

Filters documents where a specific field has no value in them.


.. code-block:: js


    {
        "constant_score" : {
            "filter" : {
                "missing" : { "field" : "user" }
            }
        }
    }


By default, the filter will only find "missing" fields, i.e., fields that have no values. It can be configured also to find fields with an explicit **null_value** mapped for them. Here is an example that will both find missing field that don't exists (**existence** set to **true**), or have null values (**null_value** set to **true**).


.. code-block:: js


    {
        "constant_score" : {
            "filter" : {
                "missing" : { 
                    "field" : "user",
                    "existence" : true,
                    "null_value" : true
                }
            }
        }
    }



Caching
=======

The result of the filter is always cached.

