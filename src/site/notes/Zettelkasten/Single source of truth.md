---
{"dg-publish":true,"permalink":"/zettelkasten/single-source-of-truth/","title":"Single source of truth","tags":["core/tech/fundamentals/design-patterns"],"noteIcon":"","created":"2023-10-27T11:42:54.946+01:00"}
---


# Single source of truth

## What is Single source of truth principle?

For every data type defined in your app (i.e a `Note` or `User` type) you **should assign** a Single Source of Truth (**SSOT**) to it. So this SSOT is the *owner* of that data and only he can **expose the data using a inmutable type**, and to modify data the SSOT exposes methods that are accessible from other layers. (This should be the `Repository` calling an `API` or `Dao` for a data base).

In an offline-first application, the source of truth for application data is typically a database.

This pattern brings multiple benefits:
- It centralises all the changes to a particular type of data in one place.
- It protects the data so that other types cannot interfere with it.
- It makes changes to the data more traceable. Thus, bugs are easier to spot.

## Relates to
## References
