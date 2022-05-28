# Exposing field table names in the C array of MYSQL_FIELD Struct reponses, as an Array of Strings in Ruby

## Problem
:as=>:hash will overwrite the first instance of the field (from the first table), with subsequent instances the field (from other tables), 
unless the SELECT statement's fields are aliased with 'as', to make them unique. Alternately, :as=>:array can be used, with indexes.

## Suggested addition to result.c

The 'table', 'org_table', 'db', 'org_db', 'org_name', and a few others, are currently not accessible from Ruby.
Exposing the MYSQL_FIELD array, either in its entirety as an Array of Structs, or just exposing the 'table' field 
as an Array of Strings, would allow introspection of multi-table query responses. 

This code just exposes 'char *table' as an Array of Strings, being a common use case. 



