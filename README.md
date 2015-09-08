=============
ckanext-odata
=============

This CKAN extension provides a basic OData 3.0 endpoint for CKAN.

The endpoint requires data to be held in the CKAN Datastore.
An _OData Endpoint_ link is added to resources, showing up as an additional endpoint when the Data API button is pressed.

Usage
-----
This implementation supports the following [OData parameters](http://www.odata.org/documentation/odata-version-3-0/odata-version-3-0-core-protocol/):
* $skip - number of records to skip from top (default: 0)
* $top - number of records to return (default:500)

The OData protocol also has support the $filter clause.  However, implementing one is non-trivial as its a dialect that doesn't directly map to PostgreSQL.

Instead, we implemented a $sqlfiter clause, where the use can specify a PostgreSQL where clause.  In our view, this is actually a more powerful implementation as you have full access to PostgreSQL's filtering capabilities which is a superset of the OData $filter clause.


Installation
------------

Installation as standard for CKAN.
This extension can be enabled by adding `odata` to the `plugin` line
in the CKAN configuration file.
