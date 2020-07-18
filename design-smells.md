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
>Code smell is a **recurring micro-structure** in the source code that may indicate the **manifestation of a design problem**
>A design problem can manifest itself in a program by affecting multiple source code locations. Each of these locations are called here smelly code
>Developer can analyze  the smelly code to identify a design problem.

### Types Of Code Smell
|Type| Description |
|--|--|
| God class | Long and complex class that centralizes the intelligence of the system |
|Brain method|Long and complex method that centralizes the intelligence of a class |
|Data Class |Class that contains data but not behavior related to the data|
|Dispersed coupling|The case of an operation which is excessively tied to many other operations in the system, and additionally these provider methods that are dispersed among many classes|
|Feature envy|Method that calls more methods of a single external class than the internal methods of its own inner class
|Intensive coupling|When a method is tied to many other operations in the system, whereby these provider operations are dispersed only into one or a few classes|

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0OTI4Njc0NDRdfQ==
-->