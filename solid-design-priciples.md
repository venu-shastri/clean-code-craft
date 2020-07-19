# Obejct Oriented Thinking

>I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages (so messaging came at the very beginning – it took a while to see how to do messaging in a programming language efficiently enough to be useful). (…) OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things.
—**Dr. Alan Curtis Kay, American computer scientist, July 23, 2003 [Ram03]**

**Object orientation (OO)** is primarily a **mindset**, and less a matter of the language used. And it can also be **abused** and **misapplied**

### Main Challenges
- How do I find and form the objects?
- How do I design the public available interface of those cells?
- How do I govern who can communicate with whom (dependencies)?

#### Abstraction – the Key to Master Complexity

#### Guiding Principles for Object Oriented Decomposition
- Information hiding ,
-  Strong cohesion,
-  Loose coupling 
-  Single Responsibility

#### Principles for Good Class Design
- Keep Classes Small
	- no more than 50 lines of code for a single class.
	- Object Calisthenics: 9 steps to better software design today” by Jeff [Object Calisthenics](https://www.cs.helsinki.fi/u/luontola/tdd-2009/ext/ObjectCalisthenics.pdf)
- Avoid God Objects

## SOLID 

### OCP
> All systems change during their life cycles. This must be borne in mind when developing systems expected to last longer than the first version.
—Ivar Jacobson, Swedish computer scientist, 1992

### LSP
> Basically the Liskov Substitution Principle states that you cannot create an octopus by extending a dog with four additional fake legs.
—Mario Fusco (@mariofusco), September 15, 2013, on Twitter

>Let q(x) be a property provable about objects x of type T. Then q(y) should be provable for objects y of type S, where S is a subtype of T.
—Barbara Liskov, Jeanette Wing [Liskov94]

> Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.
—Robert C. Martin [Martin96]

>The Liskov Substitution Principle stipulates the following rules for type respectively class hierarchies

> Whenever you are compelled to use RTTI in your program to distinguish between different types, it is a distinct “design smell,” that is, an obvious indicator for a bad object-oriented software design
- The preconditions of a base class cannot be strengthened in a derived subclass.
- Post conditions of a base class cannot be weakened in a derived subclass
- All in-variants of a base class must not be changed or violated through a derived subclass.
- The History constraint (a.k.a. the “History rule”): The (internal) state of objects should only be changed by method calls at their public interface (encapsulation). Since derived classes may introduce new attributes and methods that do not exist in the base class, the introduction of these methods may allow state changes in objects of the derived class that are not allowed in the base class. The so-called History constraint prohibits this. For instance, if the base class is designed to be the blueprint for an immutable object , the derived class should not invalidate this property of immutability with the help of newly introduced member functions.

### The Acyclic Dependency Principle 
>states that the dependency graph of components or classes should
have no cycles

> Use Dependency Inversion principle to eliminate Circular Dependency

### Don’t Talk to Strangers (Law of Demeter)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY0NzY5OTg0MywtMTgyNjI1MTc2MSwtMT
c3MDUwNDY3OCwyMDc3NzQwNjY1LC03Mjk0MzIxMDIsMTAzNzQ5
MDA4LC0xNjI1MjQ3MDEwLC0yMDg4NzQ2NjEyXX0=
-->