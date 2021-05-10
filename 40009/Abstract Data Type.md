---
aliases: [ADT]
---

### What defines an ADT?
- a set of values
- a set of operations uniformly applicable to all the values

An ADT is not characterised by data representation

An ADT should have a [[Contract]] that specifies:
- valid values
- each operation

### Implementation
There must be a [[Functional Interface]] to ensure the [[Data Type|DT]] contains all items in the [[Contract]].

Implementation requires design decisions:
- constraints of the problem
- memory vs speed
- generality vs specificity

Need to choose [[Data Representation]] and algorithms for each operation.
- data representation **must be private**
- data representation must cover **all possible values**
- algorithms must be consistant with the representation

Brings in [[Encapsulation]].

### Examples
Examples in [[Java]] could be:
- [[Undirected Graph]].
- [[Tree]].
- [[Collections]].

#C40009