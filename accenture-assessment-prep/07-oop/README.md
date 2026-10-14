# Object-Oriented Programming (OOP)

## Concepts to learn

- **Class and object:** A class defines a type/blueprint; an object is an instance with state (data) and behavior (methods).
- **Encapsulation:** Bundle state and behavior and control access to internal details through a public interface.
- **Abstraction:** Expose essential behavior while hiding unnecessary implementation detail.
- **Inheritance:** Define a specialized class based on a more general class, subject to the language's rules.
- **Polymorphism:** A common interface can support different implementations; overridden methods can behave differently for different object types.
- **Overloading vs overriding:** Overloading uses the same method name with different parameter lists (where supported); overriding replaces inherited behavior with a compatible implementation.
- **Constructor:** Initializes a new object. Constructor syntax and inheritance behavior vary by language.
- **Interface / abstract class:** Both can describe contracts or shared abstractions; exact capabilities differ by language.
- **Composition:** Build a type using other objects (“has-a”); it can be preferable to inheritance when a subtype relationship is not genuine.
- **Access control:** Public/private/protected-like rules limit which code can access members; exact semantics vary.

## Original practice MCQs

### Questions

1. A blueprint defining fields and methods for `Car` objects is a:
   A) Class  B) Loop  C) Packet  D) Database transaction

2. Hiding internal state and exposing controlled operations is:
   A) Encapsulation  B) Iteration  C) Routing  D) Normalization

3. Exposing what an object does without exposing implementation details is:
   A) Abstraction  B) Indexing  C) Compilation  D) Serialization only

4. A `SavingsAccount` derives from `Account` and reuses or specializes its behavior. This is:
   A) Inheritance  B) Hashing  C) Filtering  D) Scheduling

5. Which concept allows different classes to provide their own implementation of a shared operation?
   A) Polymorphism  B) Deadlock  C) Paging  D) DNS

6. A method has the same name but different parameter lists in a language that supports this feature. This is commonly:
   A) Overloading  B) Overriding  C) Encapsulation  D) Aggregation

7. A class's initialization routine is commonly called a:
   A) Constructor  B) Router  C) Query  D) Scheduler

8. A `Car` object contains an `Engine` object. This is an example of:
   A) Composition / has-a relationship  B) Is-a inheritance  C) Recursion  D) Encryption

### Answer key and explanations

1. **A — Class.** Objects are instances created from a class definition.
2. **A — Encapsulation.** It controls access to an object's internal representation.
3. **A — Abstraction.** The user of the type sees the essential interface, not every implementation detail.
4. **A — Inheritance.** The derived type is based on a parent/base type.
5. **A — Polymorphism.** The same interface can invoke type-specific behavior.
6. **A — Overloading.** The parameter signature differs; overriding instead replaces inherited behavior.
7. **A — Constructor.** It establishes the initial state of an object.
8. **A.** A car has an engine; an engine is not a kind of car.
