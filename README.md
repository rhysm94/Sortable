# Sortable

A reusable RAML 1.0 Trait for RESTful collection endpoints which can be sorted.
Using RAML trait parameters, you can pass an array of valid sort parameters, as demonstrated below.


```raml
#%RAML 1.0
title: Sample API

traits:
  Sortable: !include Sortable.raml

/endpoint:
  get:
    is:
      - Sortable:
          sortParams:
            - foo
            - bar
    # Or, using the (uglier) RAML/JSON syntax
    # [ Sortable: { sortParams: [ foo, bar ] } ]
```

*Some* RAML parsers complain that sortParams should be a string, but Mulesoft's RAML tooling (Anypoint Platform, Studio, Exchange, Console)
accept it as valid RAML and will restrict the `sortBy` query parameter to the values provided.
