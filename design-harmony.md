Harmony

>An application, a class, a method and any other artifact in a software system should be implemented in an harmonious way, e.g., a class has to implement an appropriate number of methods of appropriate size, complexity, and functionality.
>Appropriateness is a kind of harmony that can indeed be measured and reached

#### Three distinct harmonies that concern every software artifact

- **Identity Harmony** – `“How do I define myself?”` Every entity in a software system must justify its existence: does it implement a specific concept and how does it do that? Is it doing too many things or nothing at all?
- **Collaboration Harmony** – `“How do I interact with others?”` Every entity collaborates with others to fulfill its tasks. Does it do that all on its own, or does it use other entities. How does it use them? Does it use too many?
- **Classification Harmony** `“How do I define myself with respect to my ancestors and descendants?”`. This harmony combines elements of both identity and collaboration harmony in the context of inheritance. For example, does a subclass use all the inherited services, or does it ignore some of them?

## Identity Disharmonies
> Identity disharmonies are design flaws that affect single entities such as classes and methods
#### Rules of Identity Harmony
>**Propotion Rule**  
>Operations and classes should have a harmonious size i.e., they should avoid both size extremities. Be unique – When classes have a harmonious identity, then each
piece of concrete functionality has a unique place, i.e., it is implemented once and only once Consequently, code duplication is avoided

>**Presentation Rule**
> Each class should present its identity (i.e., its interface) by a set of services, which have one single responsibility and which provide a unique behavior

> **Implementation Rule** 
> Data and operations should harmoniously collaborate within the class to which they semantically belong
Operations belong to classes - avoid as much as possible global operations.
• Keep data close to operations – Data and the operations that use
it most should be placed as close as possible to one another. In other words, data (e.g., attributes, local variables, etc.) should stay in the class or method where they are used the most.
• Distribute complexity – The functionality provided by a class should be distributed among its operations in a balanced manner.
• Operations use most attributes – Within the same class, most operations should collaborate and use most of the data most of the time . Thus, avoid abstractions with disjunct sets of behavior and data.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4MDE0MDIyLDQ2NzM0NDg3Ml19
-->