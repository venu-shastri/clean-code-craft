
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
>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEyOTU1Nzk1NCwtNTEwMjU4MTUsNTkzOD
Q2ODA4LDgzNjMxNDc4Niw1ODY2NjQzOTYsLTE4MDMzMjIzMSwt
Mjk3Njg0NDg0LDEwMDgwODM0OTZdfQ==
-->