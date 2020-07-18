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
- GuideLines
	- Make sure that your comments add value to the code.
	- Explain always the Why, not the How.
	- Try to be as short and expressive as possible
	- Documentation Generation from Source Code
		- Doxygen (http://doxygen.org)
## Functions
- CYCLOMATIC COMPLEXITY
>The quantitative software metric cyclomatic complexity was developed by Thomas J. McCabe, a U.S.- American mathematician, in 1976.
The metric is a directly count of the number of linearly independent paths through a section of source
code, for example, a function. If a function contains no if- or switch-statement, and no for- or while-loop, there is just one single path through the function and its cyclomatic complexity is 1. If the function contains one if-statement representing a single decision point, there are two paths through the function and the cyclomatic complexity is 2.
If cyclomatic complexity is high, the affected piece of code is typically more difficult to understand, test, and modify, and thus prone to bugs.

### Bad Smells in Functions
- Too long, 
-  Has a high cyclomatic complexity
- Mixes different concerns, 
- Has many arguments, and contains dead code.

### Best Practices
#### Function Naming
- The name of a function should start with a verb. Predicates, that is, statements about an object that can be true or false, should start with “is” or “has
- The name of a function should express its intention/purpose, and not explain how it works.
#### Arguments and Return Values
##### Number of Arguments
>The ideal number of arguments for a function is zero (niladic). Next comes one (monadic), followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification  and then shouldn’t be used anyway.
— Robert C. Martin, Clean Code [Martin09]
>This is a bit weird because a function in the pure mathematical sense (y = f(x)) always has at least one argument . This means that a “function without arguments” usually must have some kind of side effect

**why are too many arguments bad?**
- Every argument in a function’s argument list can lead to a dependency
	- If function use a complex type (e.g., a class) in a function’s
argument list, then code depends on that type. The header file containing the used type must be included
- every argument must be processed somewhere inside of a function (if not, the argument is unnecessary and should be deleted immediately).

> Real functions should have as few arguments as possible. One argument is the ideal number. Member functions (methods) of a class often have no arguments. Usually those functions are manipulating the internal state of the object, or they are used to query something from the object.

#### Avoid Flag Arguments
>A flag argument is a kind of argument that tells a function to perform a different operation depending on its value. Flag arguments are mostly of type bool, and sometimes even an enumeration
	- The basic problem with flag arguments is that it will introduce two (or sometimes even more) paths . It means that the function is not doing one thing exactly right. Results case of weak cohesion  and violates the Single Responsibility Principle.
#### Avoid Output Arguments
>An output parameter, sometimes also called a result parameter, is a function argument that is used for the function’s return value.
One of the frequently mentioned benefits of using output arguments is that functions that use them can pass back more than one value at a time
- Output arguments are unintuitive and can lead to confusion.
	- whether a passed object is treated as an output parameter and will possibly be mutated by the function.
	- output parameters complicate the easy composition of expressions
		- If functions have only one return value, they can be interconnected quite easily to chained function calls
	- if immutability should be fostered and side effects must be reduced, then output parameters are an absolutely terrible idea.

>If a method should return something to its callers, let the method return it as the methods return value. If the method must return multiple values, redesign it to return a single instance of an object that holds the values. Alternatively, a **`std::tuple  or a std::pair`** can be used.

#### Don’t Pass or Return 0 (NULL, nullptr)
- A NULL or nullptr can mean failure, can mean success, and can mean almost anything
- If it is inevitable to return a regular pointer as the result from a function or method, do not return nullptr!
- you’re forced to return a regular pointer as the result from a function ensure that the pointer you’re returning always points to a valid address
- The main rationale why you should not return nullptr from a function is that you shift the responsibility to decide what to do onto your callers. They have to check it. They have to deal with many null checks,
- If a function can return a valid pointer or nullptr, it introduces an alternative flow path that needs to be continued by the caller. And it should lead to a reasonable and senseful reaction
- Any null check is forgotten, this can lead to critical runtime errors. Dereferencing a null pointer will lead to a segmentation fault and your application crashes.
- In C++ there is still another problem to consider: **`object ownership`**
	- what to do with the resource pointed to by the pointer after its
usage.
		- Who is its owner? 
		- Is it required to delete the object? If yes: How is the resource to be disposed? 
		- Must the object be deleted with delete, because it was allocated with the new operator somewhere inside the	function? Or is the ownership of the resource object managed differently, so that a delete is forbidden and	will result in undefined behavior
> if the caller does not handle the pointer correctly, it can lead to serious bugs, for example, memory leaks, double deletion, undefined behavior, and sometimes security vulnerabilities.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNzQyNzAzNTIsLTEzMTI5NzUzNzQsMT
QxMjUxNDM4LC0xNTY1OTYwNDc0LC0xNjI3ODE3NjAzLC00NzAw
NjIzNjMsODI1Njk2MjU3LC05MDAzNTY5MTMsLTIzNjMzNjA3LD
EyNDMzNTc5ODgsMTg0MzAxNTI1NiwxMDczMjg4OTI3LDE3NzQ5
ODgzMDgsMTI0NjM4MjYwNiwtMTcwNzA2ODI3LC0xMTc0MzI1Mj
E1LC0xODU2NjU0MzA0LC0yODY0NzY2NTcsMTU1MTQwNTMzNiwx
MTI5MTUwODc2XX0=
-->