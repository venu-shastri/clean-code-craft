
### Primitive Obsession
---
> Primitive Obsession is using primitive data types to represent domain ideas
> For example, we use a String to represent a message, an Integer to represent an amount of money, or a Struct/Dictionary/Hash to represent a specific object.
> **The Fix**: Typically, we introduce a **ValueObject** in place of the primitive data
> For example, instead of scattering all the parsing/formatting behavior for dates stored as text, introduce a DateFormat class which attracts that behavior as methods called parse() and format(), almost like magic
> **ValueObject** is a measure or description of something. Their identity is based on their state rather than on their object identity. This way, you can have multiple copies of the same conceptual value object. _Every $5 note has its own identity (thanks to its serial number), but the cash economy relies on every $5 note having the same value as every other $5 note_
### Data Clumps
---
>Whenever two or three values are gathered together – turn them into a $%#%^ object.” - Martin
>Data clumps are when more than one piece of data is oftentimes found together
>A data clump is a collection of two or more bits of information that are consistently used together. You’ll find that your data loses its meaning when you remove items from the clump
>A good way to identify a **data clump is that when one of the pieces does not make sense in isolation but only makes sense together**.
>Martin Fowler suggests replacing these clumps with a single object. Iexample  the startXXXX and endXXXX could be replaced by a "Range" class

### **Object Oriented Abusers** 
---
Object Oriented Abusers are a particular genre of Code Smells which refers to incorrect or incomplete implementation of Object Oriented Concepts.

#### Switch Case
---
- Violation of **Open Closed Principle**
- Replace Conditional With **Polymorphism**, typically done using the **Strategy Pattern**
- _Polymorphism gives you many advantages. The biggest gain occurs when the same set of conditions appears in many places in the program. If you want to add a new type, you have to find and update all of the conditionals. But with subclasses, you just create a new subclass and provide the appropriate methods. Clients of the class don't need to know about the subclasses, which reduces the dependencies in your system and makes it easier to update._
- When you get the SwitchStatementsSmell, it's an indication that your code isn't ObjectOriented

#### Temporary Fields
----
>There are times the developer decides to introduce Fields in the Class which are used only by one Method, instead of passing it as method parameter to avoid **Long Parameter List**. These fields sit idle in the class at all time, except when the particular method is used.

#### Alternative Classes with Different Interfaces
>This smell occurs when two methods in different classes do the same thing but have a different method signature
>**categories of different tunes with equal performance** .

>When many people develop the system together, different people may write similar code to deal with the same problem, but due to poor communication, each other did not notice this phenomenon. Therefore, these functions are similar or the same code, with different interfaces (different names or parameters) exist in the system at the same time
>**For example**, in the program, a string needs to be split into different substrings based on certain tokens. Some developers may directly use Javastring objects plus formal notation for processing, some people write their own split() public function, and some people write a function with the same function but named subString(). For the same function, if there is a unified approach, it will be easier for future maintenance, system expansion, and debugging
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1MzM5OTg3NCwtMTA2Njk1NjM3OCwxMT
I5NTU3OTU0LC01MTAyNTgxNSw1OTM4NDY4MDgsODM2MzE0Nzg2
LDU4NjY2NDM5NiwtMTgwMzMyMjMxLC0yOTc2ODQ0ODQsMTAwOD
A4MzQ5Nl19
-->