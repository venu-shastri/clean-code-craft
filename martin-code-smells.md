
### Primitive Obsession
---
> Primitive Obsession is using primitive data types to represent domain ideas
> For example, we use a String to represent a message, an Integer to represent an amount of money, or a Struct/Dictionary/Hash to represent a specific object.
> **The Fix**: Typically, we introduce a **ValueObject** in place of the primitive data
> For example, instead of scattering all the parsing/formatting behavior for dates stored as text, introduce a DateFormat class which attracts that behavior as methods called parse() and format(), almost like magic
> **ValueObject** is a measure or description of something. Their identity is based on their state rather than on their object identity. This way, you can have multiple copies of the same conceptual value object. _Every $5 note has its own identity (thanks to its serial number), but the cash economy relies on every $5 note having the same value as every other $5 note_
### Data Clumps
---
>Whenever two or three values are gathered together – turn them into a $%#%^ object.”
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4Nzk1MTkxNywxMDA4MDgzNDk2XX0=
-->