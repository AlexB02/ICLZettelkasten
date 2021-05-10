---
aliases: [Lock]
---

If an object is common between [[Thread]]s then it must be locked before and after usage. 

A variable can be locked using `synchronised()` method or by `object.lock()` and unlocked by closing the `synchronised()` branch or by `object.unlock()`. 

#C40009 