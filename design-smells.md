# Basic Concepts
## Design Problem
>A design problem is a characteristic in the software
design that leads to negative impact on maintainability .
Design problems affect program locations such as **`packages, interfaces, hierarchies, classes, and other structures`** that are relevant for the design of the system

### Description of design problems
|  Name | Description |
|--|--|
| Fat interface | Interface of a design component that offers only general, ambiguous entry-point that provides non-cohesive services, thereby complicating the clients’ logic |
|Unwanted Dependency|Dependency that violates an intended design rule|
|Component overload|Design components that fulfill too many  responsibilities
|Cyclic dependency|Two or more design components that directly or indirectly depend on each other
|Delegating abstraction|An abstraction that exists only for passing messages from one abstraction to another
|Scattered concern|Multiple components that are responsible for realizing a crosscutting concern
|Overused interface|Interface that is overloaded with many clients accessing it, that is, an interface with too many clients
|Unused abstraction |Design abstraction that is either unreachable or never used in the system

## Smelly Code / Code Smell
>Code smell is a recurring micro-structure in the source code that may indicate the manifestation of a design problem
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzQ5ODAxMjQ4XX0=
-->