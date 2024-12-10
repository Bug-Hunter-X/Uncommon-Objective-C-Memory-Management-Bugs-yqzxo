# Uncommon Objective-C Memory Management Bugs
This repository demonstrates some uncommon yet critical bugs related to memory management in Objective-C.  These errors, often subtle, can lead to crashes, unexpected behavior, or memory leaks. The examples highlight best practices for avoiding such issues.

## Bugs

* **Memory Leaks:** Improper handling of object ownership (retain/release) causes memory leaks.
* **Crashes from Delayed Selectors:**  Using `performSelector:withObject:afterDelay:` without lifecycle awareness can lead to crashes if the object is deallocated before the selector is performed.
* **Observer Issues:**  Forgetting to remove observers from notifications or delegates when they are no longer needed can lead to unpredictable program behavior.

## Solutions

The `bugSolution.m` file provides corrected versions of the code in `bug.m`, addressing the identified memory management issues. This includes properly releasing objects and using techniques to prevent crashes related to delayed selectors and unremoved observers.

## Learning Points

* Always pay close attention to object ownership in Objective-C and use ARC effectively.
* When using delayed selectors ensure the object is still valid. Consider alternatives like GCD for more robust timers.
* Be diligent about removing observers when they are no longer needed, avoiding potential crashes and unexpected behavior.