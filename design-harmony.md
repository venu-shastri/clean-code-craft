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
- Operations and classes should have a harmonious size i.e., they should avoid both size extremities
- Each class should present its identity (i.e., its interface) by a set of services, which have one single responsibility and which provide a unique behavior
- Data and operations should harmoniously collaborate within the class to which they semantically belong


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2ODk5NDQ2NTgsNDY3MzQ0ODcyXX0=
-->