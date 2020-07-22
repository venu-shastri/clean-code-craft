# Obejct Oriented Thinking

>I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages (so messaging came at the very beginning – it took a while to see how to do messaging in a programming language efficiently enough to be useful). (…) OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things.
—**Dr. Alan Curtis Kay, American computer scientist, July 23, 2003 [Ram03]**

**Object orientation (OO)** is primarily a **mindset**, and less a matter of the language used. And it can also be **abused** and **misapplied**

### Main Challenges
- How do I find and form the objects?
- How do I design the public available interface of those cells?
- How do I govern who can communicate with whom (dependencies)?

#### Abstraction – the Key to Master Complexity
---
>Once you realize that computing is all about constructing, manipulating, and reasoning about abstractions, it becomes clear that an important prerequisite for writing (good) computer programs is the ability to handle abstractions in a precise manner. As it happens, that is something we humans have been doing successfully for more than three thousand years. We call it mathematics 
>-(Devlin, 2003)

>Abstraction is the selective examination of certain aspects of a problem,
Abstraction must always be for a purpose, because the purpose decides what is and is not important. 
A good model captures the crucial aspects of a problem and omits the others. (Rumbaugh et al., 1991)

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
>  known as the Principle of Least Knowledge

>  The Law of Demeter can be regarded as a principle that says something like “Don’t talk to strangers”, or “Only talk to your immediate neighbors.”
#### Rules
- A member function is allowed to call other member functions in its own class scope directly.
-  A member function is allowed to call member functions on member variables that are in its class scope directly.
-  If a member function has parameters, the member function is allowed to call the member functions of these parameters directly.
-  If a member function creates local objects, the member function is allowed to call member functions on those local objects.
Object form of Law of Demeter (DemeterW3; Martin, 2003)
### Simplified (Martin)
A method m of a class C, can only call methods of:
• C
• An object passed as an argument to m.
• An object created by m.
• An object held in an instance variable of C

### ISP
-----------------------------------------------------------------------------------
Example from Martin (2003): In a security system there are Door objects that can be locked and unlocked, and they know whether they are locked or not. In the spirit of the DIP, the Door class is made abstract thereby allowing clients to use objects with this behaviour without having to depend on a particular implementation . A TimedDoor is an implementation of Door that sounds an alarm when when the door has been left open too long. To manage this, the TimedDoor object collaborates with a Timer object. The Timer object keeps a reference to a TimerClient object whose timeOut method is to be called when time expires.-
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDUzMzA4Nzg2LC0xODU0OTk4NDIyLC0xMj
E0ODk0NDg0LC0xNzA1MjEzODc2LC02MTA4NjAxODQsLTE4MjYy
NTE3NjEsLTE3NzA1MDQ2NzgsMjA3Nzc0MDY2NSwtNzI5NDMyMT
AyLDEwMzc0OTAwOCwtMTYyNTI0NzAxMCwtMjA4ODc0NjYxMl19

-->