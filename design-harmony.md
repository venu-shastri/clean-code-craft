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
			
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI4OTMzOTE0OCw5MjQ3NjI0ODksMTg4MD
E0MDIyLDQ2NzM0NDg3Ml19
-->