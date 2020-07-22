
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

#
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3MDE3Mjc1NSw4MzYzMTQ3ODYsNTg2Nj
Y0Mzk2LC0xODAzMzIyMzEsLTI5NzY4NDQ4NCwxMDA4MDgzNDk2
XX0=
-->