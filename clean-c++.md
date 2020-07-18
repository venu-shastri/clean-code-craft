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
- 
	

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ1MTI0MDA1MiwxMTI5MTUwODc2LDE1OD
M0MDE3MDEsMTI2MDAwNjA5NiwxNzA1MTM2NTUwLC0xMDQ1MjMx
NzYzXX0=
-->