Harmony

>An application, a class, a method and any other artifact in a software system should be implemented in an harmonious way, e.g., a class has to implement an appropriate number of methods of appropriate size, complexity, and functionality.
>Appropriateness is a kind of harmony that can indeed be measured and reached

#### Three distinct harmonies that concern every software artifact

- **Identity Harmony** – `“How do I define myself?”` Every entity in a software system must justify its existence: does it implement a specific concept and how does it do that? Is it doing too many things or nothing at all?
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
- **Collaboration Harmony** – `“How do I interact with others?”` Every entity collaborates with others to fulfill its tasks. Does it do that all on its own, or does it use other entities. How does it use them? Does it use too many?
- **Classification Harmony** `“How do I define myself with respect to my ancestors and descendants?”`. This harmony combines elements of both identity and collaboration harmony in the context of inheritance. For example, does a subclass use all the inherited services, or does it ignore some of them?

## Identity Disharmonies
> Identity disharmonies are design flaws that affect single entities such as classes and methods
- **`God Class`**
	- This design problem is comparable to Fowler’s **Large Class** bad smell
	- How to Detect
		- They heavily access data of other simpler classes, either directly or using accessor methods.
		- They are large and complex
		- They have a lot of non-communicative behavior i.e., there is a low
cohesion between the methods belonging to that class.
	- Refactoring
		- identify clusters of methods and attributes that are tied together and to extract these islands into separate classes
		- incrementally redistribute the responsibilities of the God Class either to its collaborating classes or to new classes that are pulled out of the God Class

- **`Feature Envy`**
	- Causes poor data - operation proximity , results in a change in a method triggers changes in other methods and so on; the same applies for bugs
	-  How to Detect
		- Method uses directly more than a few attributes of other classes
		- Method uses far more attributes from other classes than its own.
		- The used “foreign” attributes belong to very few other classes
- **`Data Class`**
	- dumb” data holders without complex functionality but other classes strongly rely on them
	- Data Classes are the manifestation of a lacking encapsulation of data, and of a poor data-functionality proximity
	- Data Classes break design principles
because they let other classes see and possibly manipulate their data, leading to a brittle design
	- Detection
		- search for **`lightweight`** classes
			- Interface of class reveals data rather than offering services
		- look for the classes that define many accessors (get/set methods) and for those who declare data fields in their interfaces

- **`Brain Method`**
	- Often a method starts out as a “normal” method but then more and more functionality is added to it until it gets out of control, becoming hard to maintain or understand
	- Brain Methods   are harder to understand and debug, and practically impossible to unit test
	- Detection
		- Convergence of three simple code smells described by Fowler
			- Long methods
				- many temporary variables and parameters
			- Excessive branching
				- intensive use of switch statements (or if–else–if) 
			- Many variables used
				- many local variables but also many instance variables.
	- Refactroing
	> whenever we feel the need to comment something, we write a method instead. Such a method contains the code that was commented but is named after the intention of the code rather than how it does it.
	--Martin
- **`Brain Class`**
- complex classes that tend to accumulate an excessive amount of intelligence, usually in the form of several methods affected by Brain Method
- Detection
	- Class contains more than one Brain Method(92) and is very large.
	- Class contains only one Brain Method(92) but is extremely large and complex
	- Class is very complex and non-cohesive
	>Brain Class detection strategy is trying to
complement the God Class strategy by catching those excessively complex classes that are not detected as God Classes either because they do not abusively access data of “satellite” classes, or because they are a little more cohesive

- **`Significant Duplication`**
	- What is significant
		- It is the largest possible chain of duplication that can be formed in that portion of code, by uniting all islands of exact clones that are close enough to each other.
		- It is large enough.
	- Code duplication harms the uniqueness of entities within a system.
	- If duplication appears, it becomes
much harder to locate errors because the assumption “only class X implements this, therefore the error can be found there” does not hold anymore
	- Two cases of duplication
		- Copy-Paste-Case
		- Copy-Paste-Adopt
	- eliminate duplication using Beck’s Once and Only Once Rule
	- >By eliminating the duplicates, you ensure that the code says everything once and only once, which is the essence of good design
	--Beck
	Means put all “instances” of a duplicated
portion of code into one single location
**what is the proper location?**
		-Look for context of the duplicated entities
Three different contexts in which duplication appears
Case I: Duplication Within the Same Class
Case II: Duplication Within the Same Hierarchy
Case III: Duplication Within Unrelated Classes


## Collaboration Collaboration Harmony

### Rule
>Collaborations should be only in terms of method
invocations and have a limited extent, intensity and
dispersion

>You want to leverage the services of other classes, but you want to have services at the right level, so that you want to know only about a limited number of objects and their services. [...] If you had to interact with all the indirectly related objects, we’d have a tangled web of inter-dependencies and maintenance would be a nightmare
--Lorenz and Kidd
#### intensity – 
>Operations should collaborate (mainly unidirectional) with a limited number of services provided by other classes

### extent – 
> Operations (and consequently their classes) should collaborate with operations from a limited number
of other classes.

### dispersion –
 The collaborators (i.e., invoked and/or invoking operations) of an operation should have a limited
dispersion within the system. Thus, one should try to make an entity collaborate closely only with a selected set of entities, with a preference for entities  located in the
 (0) same abstraction; 
 1) same hierarchy; 
 (2) same package (or subsystem).

### Note
The term Collaborate refers both to the active (i.e., call another operation) and to the passive (i.e., be called (invoked) by another operation) aspects.

### Collaboration Disharmonies

####  Intensive Coupling
----
- when a method is tied to many other operations in the system
- The communication between the client method and (at least one of) its provider classes is excessively verbose
-impact 
 >An operation which is intensively coupled with methods from a handful of classes binds it strongly to those classes
 >Understanding the relation between the two sides (i.e., the client method and the classes providing services) becomes more difficult
- Detection Strategy
-Two following conditions that must Detection be fulfilled simultaneously
- The function invokes many methods and
the invoked methods are not very much dispersed into many classes

- Refactoring
	- Define a new service in the provider class and replace the multiple calls with a single call to the newly defined method

####  Dispersed Coupling
----
- An operation which is excessively tied to many other operations in the system, and additionally these provider methods that are dispersed among many classes
- single operation communicates with an excessive number of provider classes, whereby the communication with each of the classes is not very intense i.e., the operation calls one or a few methods from each class.
- Impact
>Dispersively coupled operations lead to undesired ripple effects, be- Impact cause a change in an dispersively coupled method potentially leads to changes in all the coupled and therefore dependent classes
- Detection Strategy
	- capture only those operations that have a high dispersion of their coupling
		- Operation calls a few methods from each of a    large number of unrelated classes
- Note
>In many cases the operation that exhibits Dispersed Coupling is also a Brain Method  because An excessively
large and complex operation is almost always non-cohesive, doing more than one thing; and therefore there will be many invocations to methods from many classes
- Refactoring
	- Anything in the client method (i.e., the
one affected by Dispersed Coupling)that could be moved to one of the lightweight methods that it invokes

#### Shotgun Surgery
---
>change in an operation implies many (small) changes to a lot of different operations and classes 
>Concerns Spread Everywhere

- Impact
	- Changes become more time-consuming, since you have to edit your codebase in more places.
	-  Merge conflicts become more likely, since more people are touching the code in more places. This generally makes collaborative projects more dicey.
	- You’re more likely to introduce bugs because of the cognitive load of remembering to change the code in more places. If a simple feature requires you to make changes in 7 files, there’s a decent chance you won’t remember all 7. This can lead to more labor-intensive QA efforts and even to production defects.
	- You wind up with more code, due to the fact that you’ll have knowledge duplication and more constructs required to glue the various disparate pieces together.
	- The learning curve is higher for new team members, since development is something of a treasure hunt

- Detection
	- Operation is called by too many other methods
	- Incoming calls are from many classes
	- Audit your source control tool, or else just mentally pay attention to how many files you’re touching while making conceptually simple changes. If it’s a lot, then you’ve got an issue.
	- 
## Classification Harmony 
- The object-oriented programming paradigm captures the is-a-kind-of relationship among classes with **inheritance** . Inheritance is at the same time a curse and a blessing of the object oriented paradigm .Inheritance should be used with care and style.

#### Rules
---

	
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk1MTYwODMzMywtMzU0NzI4NDA4LDEyMj
Y1MjMyODgsMTkzMzQ4OTI3OSwtMTE4NDM4NTEyMiwtMTQ3MTQz
MjY4MCwtMTA4NjQyMTc1NywtNzAzMDM4MDAsLTE0MTc0NDQzMD
MsNjI1MDc1NTk0LDE3NzYyNTY3NDEsLTE4MzgyMzM2OTcsLTE2
Nzk5NjE2MzQsMTcwNzQ1MzY4NCw0NzQ0MTYxODcsLTc3MTMyNj
gxNSwxMzM4ODIyMzgyLDExMzA5MDE4NjYsOTI0NzYyNDg5LDE4
ODAxNDAyMl19
-->