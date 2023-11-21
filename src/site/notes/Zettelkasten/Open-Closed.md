---
{"dg-publish":true,"permalink":"/zettelkasten/open-closed/","title":"Open-Closed","tags":["status/todo","core/tech/fundamentals/principles"],"created":"2023-10-27T12:18:03.764+01:00"}
---


# Open-Closed

### What is Open-Closed Principle?
In this principle, software components must be open for extensions but closed for modifications. Sounds weird, but let me try to explain. The structure of the code should be designed so that you can change the behavior of the class without modification of existing code but only by adding new code. You can achieve that by creating an additional abstraction level. For example, instead of multiple ‘if else if else’, create separate objects that can handle the same logic. Be careful with this principle, implement new abstract layers only when you actually need them, never when you just feel that you need them.

## Relates to
## References
