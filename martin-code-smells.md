
### Primitive Obsession
---
> Primitive Obsession is using primitive data types to represent domain ideas
> For example, we use a String to represent a message, an Integer to represent an amount of money, or a Struct/Dictionary/Hash to represent a specific object.
> **The Fix**: Typically, we introduce a **ValueObject** in place of the primitive data
> For example, instead of scattering all the parsing/formatting behavior for dates stored as text, introduce a DateFormat class which attracts that behavior as methods called parse() and format(), almost like magic
> **ValueObject** is a measure or description of something.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ1MjA5NTE5MF19
-->