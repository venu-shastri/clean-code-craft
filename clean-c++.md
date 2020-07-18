## Good Names
**Programs must be written for people to read, and only incidentally for machines to execute.**
—Hal Abelson and Gerald Jay Sussman, 1984
- Source code is read much more often by developers than translated by a compiler
- source code should be readable, and good names are a key factor to increase its readability
- Source code files, namespaces, classes, templates, functions, arguments, variables, and constants should have meaningful and expressive names.
### Few bits of advice for finding good names.
- Names Should Be Self-Explanatory
	- Use simple but descriptive and self-explaining names.
	- Too long and verbose names are not appropriate or desirable
	- If the context is clear in which a variable is used, shorter and less descriptive names are possible
	- If the variable is a member (attribute) of a class, for instance, the class’s name usually provides sufficient context for the variable
- Use Names from the Domain
	- DDD
	- Name components, classes, and functions in a way that elements and concepts from the application’s domain can be rediscovered
- Choose Names at an Appropriate Level of Abstraction
	- To keep the complexity of today’s software systems under control, these systems are usually hierarchically decomposed.
	- With such decomposition, software modules are created at different levels of abstraction: starting from large components or subsystems down to very small building blocks like classes
	- The abstraction levels introduced by this approach also have an impact on naming
	- Every time we go one step deeper down the hierarchy, the names of the elements must more concrete.
	- ex:- Imagine a Webshop. On the top level there might exist a large component whose single responsibility is to create invoices. This component could have a short and descriptive name like **Billing**. Usually, this component consists of further smaller components or classes. For instance, one of these smaller modules could be responsible for the calculation of a discount. Another module could be responsible for the creation of invoice line items. Thus, good names for these modules could be **DiscountCalculator** and **LineItemFactory**. If we now dive deeper into the decomposition hierarchy, the identifiers for components , classes, and also functions or methods become more and more concrete, verbose, and thus also longer. For
example, a small method in a class at the deepest level could have a very detailed and elongated name, like **calculateReducedValueAddedTax**().

- Avoid Redundancy When Choosing a Name
	- It is redundant to pick up a class name or other names that provide a clear context, and use them as a part to build the name of a member variable

- Avoid Cryptic Abbreviations
	- When choosing a name for your variables or constants, use full words instead of cryptic abbreviations
	- cryptic abbreviations reduce the readability of  code significantly
- Avoid Hungarian Notation and Prefixes
	- Charles Simonyi (Chief Architect at Microsoft in the 1980s) developed a notation convention for naming variables in computer software, named the Hungarian notation
	- When using Hungarian Notation, the type, and sometimes also the scope, of a variable are used as a naming prefix for that variable
	- Hungarian notation was potentially helpful in a weakly typed language
	- It may have been useful at a time when developers have used simple editors for programming, and not IDEs that have a feature like “IntelliSense.”
	- Do not use Hungarian notation, or any other prefix-based notation, encoding the type of a variable in its name!
	- In object-oriented languages that support polymorphism, the prefix cannot be specified easily, or a prefix can even be puzzling
	- How to determine a suitable and unmistakable prefix for an instantiated C++ template?
- Avoid Using the Same Name for Different Purposes
	- Once you’ve introduced a meaningful and expressive name for any kind of software entity (e.g., a class or component), a function, or a variable, you should take care about that its name is never used for any other purpose

## Comments
Truth can only be found in one place: the code.
—Robert C. Martin, Clean Code [Martin09]
- Comments are necessary when there is need for explanation and clarification	
- Let the Code Tell a Story
	- Code should tell a story and be self-explanatory. Comments must be avoided whenever possible
	- Do Not Comment Obvious Things
	- Don’t Disable Code with Comments
		- Adds confusion with no real benefit
		- Except for the purpose to try out something quickly, don’t use comments to disable code. There is a version control system!
		- If code is no longer used, simply delete it. Let it go. You have a “time machine” to get it back, if necessary: use version control system
	- Don’t Use Comments to Substitute Version Control
	- Don’t Write Block Comments
-  The Rare Cases Where Comments Are Useful
	- a comment is justified if a section of code has a high degree of inherent complexity so that it cannot be understood easily by everyone who did not have deep expert knowledge, ex:- sophisticated mathematical algorithm or formula ,The software system deals with a not everyday (business) domain ,experimental physics, complex simulations of natural phenomenons, or ambitious ciphering methods
	- Another good reason to write a comment for once is a situation in which you must deliberately deviate from a good design principle


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NTkzODI3MzIsMTg0MzAxNTI1NiwxMD
czMjg4OTI3LDE3NzQ5ODgzMDgsMTI0NjM4MjYwNiwtMTcwNzA2
ODI3LC0xMTc0MzI1MjE1LC0xODU2NjU0MzA0LC0yODY0NzY2NT
csMTU1MTQwNTMzNiwxMTI5MTUwODc2LDE1ODM0MDE3MDEsMTI2
MDAwNjA5NiwxNzA1MTM2NTUwLC0xMDQ1MjMxNzYzXX0=
-->