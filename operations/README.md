---
description: Atoms of processing.
---

# 💪 Operations

**Spignite** operation is a simple, atomic operation on a file from the set. Such operation may set some meta-data (attributes), analyze content etc; may define output links (which is also a metadata) or can even change the content of a file.

**Spignite** operations are defined on _phases_. Don't worry, the API is made in such way you can't get it wrong.

### Defining operations

There are two methods that define an operation: `op()` and `do()`.

