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
|Brain method|Long and complex method that centralizes the intelligence of a class,oversized and over complex methods  |
|Data Class |Class that contains data but not behavior related to the data|
|Dispersed coupling|The case of an operation which is excessively tied to many other operations in the system, and additionally these provider methods that are dispersed among many classes|
|Feature envy|Method that calls more methods of a single external class than the internal methods of its own inner class
|Intensive coupling|When a method is tied to many other operations in the system, whereby these provider operations are dispersed only into one or a few classes|
|Refused bequest|Subclass that does not use the protected methods of its superclass|
|Shotgun surgery|This smell is evident when you must change lots of pieces of code in different places simply to add a new or extended piece of behavior ,pops up when you have to make changes throughout the code base to implement a single requirement,This may often be caused by “copy and paste” programming|
|Tradition breaker|Subclass that provides a large set of services that are unrelated to services provided by the superclass|

### Code smells and Design Problems
>Developers can rely on the analysis of code smells to identify design problems.
>Usually, a code smell is related to a design problem when it occurs due to the presence of design problem. Developers can rely on the analysis of code smells to
identify design problems . Unfortunately, not all (instance of) code smells are related to a design problem

For Instance :- 
>Consider **Scattered Concern** , a design problem that occurs when multiple code elements implement a functionality that should have been implemented by only
a few elements. Often, elements that implement the scattered functionality contain **code smells such as God Class, Feature Envy, Intensive Coupling, Divergent Change**.
- As the code elements implement a scattered functionality,
these elements are likely of realizing at least two functionalities: their predominant functionality and another one, in which the predominant functionality can
be either the scattered one or not. Either way, the elements implement more than one functionality, which leads them to the appearance of a **God Class**. 
- Additionally, the methods in the class have to communicate with other classes
that also implement the scattered functionality. Thus, these methods can contain instances of Feature Envy, leading to the appearance of an **Intensive Coupling smell**.
- Furthermore, every chance in the functionality will impact
the elements that implement it; thus, these elements will
have the **Shotgun Surgery and Divergent Change**. 
>In summary, these code smells could appear in the elements due
to the scattered functionality, i.e., due to the Scattered
Concern.

### Stinky program location
>A program location is, the more likely it is to be affected by a design problem
>**Stinky code** is the manifestation of multiple code smells in a program location
#### Smell Agglomerations

<!--stackedit_data:
eyJoaXN0b3J5IjpbNzIzNDEzNDUwLC0xMzc5ODA2MDEwLDk1OD
g5ODIyMSwtNTMxNDM5OTMzXX0=
-->