# Clean Code: The Bootcamp Lessons

## ⭐ The Goal
- Write code that reads like a story. Clear, logical, and easy to follow.

## 1. Lesson: Meaningful Names
- **Concept**: Names must reveal intent.
- **Motto**: "If it needs a comment, the name is wrong."
- **Example**: `elapsedTimeInDays` is better than `d`.

## 2. Lesson: Banish Magic Values
- **Concept**: Give raw numbers and strings a constant name.
- **Motto**: "No magic!"
- **Example**: `if (status === ORDER_STATUS_PAID)` is better than `if (status === 2)`.

## 3. Lesson: Functions Do ONE Thing
- **Concept**: The Single Responsibility Principle for functions.
- **Motto**: "If you use 'and' to describe it, break it up."
- **Example**: `validateUser()` and `saveUser()` are better than `validateAndSaveUser()`.

## 4. Lesson: Avoid Side Effects
- **Concept**: A function should not have hidden, surprising behaviors.
- **Motto**: "No surprises."
- **Example**: `isValid()` should just return true/false, not also change a global variable.

## 5. Lesson: Use Exceptions, Not Error Codes
- **Concept**: Separate happy path logic from error handling.
- **Motto**: "`try/catch` is cleaner than `if (result === null)`."
- **Example**: Throw an `Error` for a missing user instead of returning `null`.

## 6. Lesson: Comments are a Last Resort
- **Concept**: Code should be self-documenting. Comments often mean the code is unclear.
- **Motto**: "Don't comment bad code—rewrite it."
- **Example**: `isEligible()` is better than a complex `if` with a comment above it.

## 🏕️ The Golden Rule
- **The Boy Scout Rule**: "Always leave the code cleaner than you found it."