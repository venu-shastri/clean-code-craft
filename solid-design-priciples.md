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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4MTY0MDg0LC03Mjk0MzIxMDIsMTAzNz
Q5MDA4LC0xNjI1MjQ3MDEwLC0yMDg4NzQ2NjEyXX0=
-->