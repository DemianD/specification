# Traversing Node elements

When a `tree:Node` element is found, its `tree:value` __must__ be set. The object of `tree:value` __should__ be accompanied by a data type.

The `tree:Node` element __may__ also have one or more `tree:childRelation`. A child relation is an entity of the type `tree:ChildRelation`, and __may__ have one or more more specific types. A `tree:ChildRelation` __must__ have one or more `tree:child` objects of the type `tree:Node`. In this description in all documents, this child __must__ contain a `tree:value`. If a particular child is flagged interesting after evaluating the relation, then this child’s URL needs to be followed.

Every node __may__ provide a `tree:remainingItems`. A client __may__ use `tree:remainingItems` to estimate the completeness of the downloaded elements.

## ChildRelations

When the _only_ type given for a certain ChildRelation is `tree:ChildRelation`, then the client must dereference all of its children.

Other types:
 - `tree:StringCompletesRelation` - In order to find a string, you must concatenate the value of this node with the value of the parent node, and its former parents that were linked through this relation.
 - `tree:GreaterThanRelation` and the likes - You must evaluate the value against the relation as defined by this relation. Number evaluation is straightforward. String comparisons will be further defined in Chapter 4.
 - Interval relations _TODO_ - see vocabulary for now
 - Geographic relations _TODO_ - see vocabulary for now

### Comparing strings according to a locale

When comparing strings, different strategies can be applied. Bytestring or depending on a specific locale.

_TODO: define different strategies_

# Traversing geospatial tiles

When a tile is found through tree:latitudeTile, tree:longitudeTile and tree:zoom, other elements can be found in two ways:
 1. Through a description of 
 2. A search form is exposed and all other URLs to tiles in a viewport or bounding box can be calculated

This text is for the first option. See the [Search spec](3-search.md) for the second option.
