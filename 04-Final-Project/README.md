---
name: php-oop-final-project
purpose: >
  This file has exactly one purpose: to guide one realistic final project that
  proves the student understands the PHP OOP lecture track, interview questions,
  and visual maps.
scope: >
  This file should only contain the final project plan, milestones, validation
  checklist, folder conventions, and mentor rules for the PHP OOP final project.
description: >
  Structured final-project guide for building one real-world PHP OOP project
  after finishing the lectures, interview questions, and visual maps. Trigger
  this skill when the student says "start final project", "continue final
  project", "review my final project", or asks to validate their PHP OOP
  understanding through a practical project.
triggers:
  - user wants to start the PHP OOP final project
  - user wants to continue the PHP OOP final project
  - user wants a real-world PHP OOP practice project
  - user wants to test whether they truly understand PHP OOP
  - user asks for project review after finishing lectures, interviews, and visual maps
---

# PHP OOP Final Project (PHP 8.5+) - SupportDesk Lite

> **Status:** Not started — This folder is the student's workspace for the PHP OOP final project.

## Rule

The student writes all implementation code. The mentor may guide, review, debug, and ask focused questions, but must not write the solution files.

## When To Start

Do not start this project yet.

Start only after:
1. All 31 lectures in `../01-Lectures/README.md` are completed.
2. All 42 interview questions in `../02-Interview-Questions/README.md` are completed.
3. All 12 visual maps in `../03-Visual-Maps/README.md` are completed.
4. The student explicitly says they are ready to start the final project.

This project is the final proof step. It is not a lecture replacement.

**Next step when ready:** Start with Milestone 00 in this README.

---

## Final Project Review Checklist

Use this checklist before considering the final project complete.

```
- [ ] Every milestone from 00 to 14 is marked with ✅ in the progress list.
- [ ] The project runs from `playground.php` or the chosen manual runner.
- [ ] The project uses namespaces and autoloading correctly.
- [ ] The project contains real classes, objects, properties, methods, and constructors.
- [ ] Important data is protected through encapsulation and validation.
- [ ] Enums are used for ticket status and priority.
- [ ] Interfaces are used for replaceable storage and notification behavior.
- [ ] Inheritance is used only where the relationship is truly meaningful.
- [ ] Traits, abstract classes, static members, and constants are used only where they add value.
- [ ] Exceptions represent real business failures.
- [ ] Object references, cloning, readonly values, comparison, and serialization are demonstrated.
- [ ] Advanced features such as attributes, anonymous classes, object iteration, and lazy initialization are used intentionally.
- [ ] PHPUnit tests cover the most important business behavior.
- [ ] `notes.md` explains the main design decisions in interview style.
- [ ] The student can explain every major class and design choice without reading the code line by line.
```

The project is complete only when the code works and the student can explain why the design works.

---

## Project Summary

Build **SupportDesk Lite**, a small customer-support ticketing system.

This is a real-world type of project used by SaaS products, e-commerce stores, hosting companies, internal IT teams, and service businesses.

The project stays intentionally small:
- No framework.
- No database required at first.
- No web UI required.
- No authentication system required.
- No giant architecture.

The goal is not to build a huge product. The goal is to prove that the student can design and write a complete object-oriented PHP application from scratch.

---

## Student Role (Mandatory)

**The student writes all project code. The mentor only explains, reviews, and displays examples.**

The mentor may show small code snippets in chat to explain an idea, but the student must type and save every project file in this folder themselves.

The student writes all project code.

The mentor may:
- Explain requirements.
- **Show** short annotated examples in the chat (not full solution files).
- Ask design questions.
- Review code written by the student.
- Point out missing concepts.
- Suggest the next small step.
- Help debug errors after the student shares code or error output.

The mentor must not:
- Write complete solution files.
- Create the student's `.php` implementation files.
- Build the project on behalf of the student.
- Save project code into the workspace using file-writing tools.
- Skip the student's design decisions.
- Turn this into a framework or design-pattern course.

---

## Business Scenario

A small SaaS company needs a simple support system.

Customers can open support tickets. Support agents can reply, assign tickets, change priority, and close tickets. The system stores tickets in memory first, then later saves and loads them from a file.

The business wants to answer questions like:
- What tickets are still open?
- Which tickets are urgent?
- Which agent owns a ticket?
- What happened in the ticket conversation?
- Can the ticket be exported, restored, and tested safely?

---

## Core Features

The finished project must support these actions:

1. Create a customer.
2. Create a support agent.
3. Create a ticket with a title, description, priority, and customer.
4. Assign a ticket to an agent.
5. Add public replies to a ticket.
6. Add internal notes visible only to agents.
7. Change ticket status: `Open`, `Pending`, `Resolved`, `Closed`.
8. Change ticket priority: `Low`, `Normal`, `High`, `Urgent`.
9. List tickets by status.
10. List urgent tickets.
11. Close a ticket safely.
12. Prevent invalid state changes.
13. Store tickets behind a repository interface.
14. Switch between in-memory storage and file storage.
15. Send notifications through a notification interface.
16. Export and restore ticket data.
17. Write focused tests for the most important behavior.

---

## Required Folder Structure

The student will write project files inside this folder.

```
04-Final-Project/
  README.md                      // This guide
  composer.json                  // Student-created when Composer is introduced
  src/
    Domain/
      Tickets/
        Ticket.php
        TicketId.php
        TicketStatus.php
        TicketPriority.php
        TicketMessage.php
        PublicReply.php
        InternalNote.php
      Users/
        User.php
        Customer.php
        SupportAgent.php
      Shared/
        Timestampable.php
    Contracts/
      TicketRepository.php
      Notifier.php
      Exporter.php
    Infrastructure/
      Storage/
        InMemoryTicketRepository.php
        FileTicketRepository.php
      Notifications/
        EmailNotifier.php
        LogNotifier.php
      Export/
        JsonTicketExporter.php
    Application/
      TicketService.php
      TicketSearchService.php
    Exceptions/
      TicketNotFoundException.php
      InvalidTicketStateException.php
      UnauthorizedTicketActionException.php
    Attributes/
      Sensitive.php
      AuditAction.php
  tests/
    TicketTest.php
    TicketServiceTest.php
    RepositoryTest.php
  playground.php                 // Student-created manual test runner
  notes.md                       // Student's design notes and final reflection
```

This structure is a target, not a starting dump. The student creates files gradually as each milestone requires them.

---

## Development Rules

1. Use PHP 8.5+.
2. Use `declare(strict_types=1);` in files that use type declarations.
3. Use namespaces and PSR-4 style organization.
4. Use one class, interface, enum, or trait per file.
5. Keep each class focused on one clear responsibility.
6. Do not introduce a database until the file-storage version works.
7. Do not use Laravel, Symfony, or another framework.
8. Do not copy a ready-made ticketing system.
9. Do not add features outside the checklist until the core project is complete.
10. Every important rule must be enforced by code, not by comments.

---

## Milestone Plan

### Milestone 0 - Project Setup

**Goal:** Create the project workspace and explain the first design.

The student must create:
- `notes.md`
- A first draft of the folder structure.

The student must answer:
- What problem does this project solve?
- What are the main objects in the system?
- Which parts are domain logic and which parts are infrastructure?

Completion check:
- The student can explain the project in plain English without code.

---

### Milestone 1 - First Objects

**Goal:** Build the smallest useful domain model.

The student must create:
- `Ticket`
- `Customer`
- `SupportAgent`

Required concepts:
- Class vs. object
- Properties
- Methods
- Constructor
- `$this`
- Type declarations

Behavior to implement:
- Create a customer.
- Create an agent.
- Create a ticket.
- Print or inspect ticket information manually.

Completion check:
- The student can explain which values belong as properties and which actions belong as methods.

---

### Milestone 2 - Encapsulation and Validation

**Goal:** Protect ticket data from invalid changes.

Required concepts:
- `public`, `private`, and `protected`
- Encapsulation
- Validation
- Property hooks when useful
- Asymmetric visibility when useful

Behavior to implement:
- A ticket title cannot be empty.
- A ticket description cannot be empty.
- A ticket status cannot be changed directly from outside.
- A ticket ID can be read from outside but not changed from outside.

Completion check:
- The student can explain why public mutable properties would be dangerous here.

---

### Milestone 3 - Enums and Safe State

**Goal:** Replace fragile strings with safe states.

The student must create:
- `TicketStatus`
- `TicketPriority`

Required concepts:
- Enums
- Type hints with enums
- `from()` and `tryFrom()` when converting raw values

Behavior to implement:
- Allowed statuses: `Open`, `Pending`, `Resolved`, `Closed`.
- Allowed priorities: `Low`, `Normal`, `High`, `Urgent`.
- Invalid raw status values must not silently enter the system.

Completion check:
- The student can explain why enums are safer than plain strings for ticket status.

---

### Milestone 4 - Inheritance and Shared User Behavior

**Goal:** Use inheritance only where it is truly meaningful.

The student must create:
- An abstract or base `User`
- `Customer`
- `SupportAgent`

Required concepts:
- Inheritance
- Method overriding
- `parent::`
- Protected members only when justified
- Final methods when behavior must not be changed

Behavior to implement:
- Both customers and agents have a name and email.
- Agents have an agent level or department.
- Customers and agents may display their identity differently.

Completion check:
- The student can explain why `Customer` and `SupportAgent` can share a parent, and what should not be placed in that parent.

---

### Milestone 5 - Interfaces and Polymorphism

**Goal:** Make storage and notifications replaceable.

The student must create:
- `TicketRepository`
- `Notifier`
- `InMemoryTicketRepository`
- `LogNotifier`

Required concepts:
- Interfaces
- Implementing multiple interfaces when useful
- Polymorphism
- Type hints against interfaces

Behavior to implement:
- `TicketService` saves tickets through `TicketRepository`.
- `TicketService` sends notifications through `Notifier`.
- The service must not know the concrete storage or notification class.

Completion check:
- The student can explain how a new notifier can be added without changing the service logic.

---

### Milestone 6 - Abstract Classes, Traits, and Reuse

**Goal:** Share useful behavior without forcing the wrong relationship.

The student may create:
- `TicketMessage`
- `PublicReply`
- `InternalNote`
- `Timestampable`

Required concepts:
- Abstract classes
- Traits
- Trait conflict awareness
- Constructor reuse

Behavior to implement:
- Public replies and internal notes share message text and creation date.
- Public replies and internal notes differ in visibility or display behavior.
- Repeated timestamp behavior is handled cleanly.

Completion check:
- The student can explain why a trait may be better than inheritance for timestamp behavior.

---

### Milestone 7 - Exceptions and Business Rules

**Goal:** Make failure explicit and understandable.

The student must create:
- `TicketNotFoundException`
- `InvalidTicketStateException`
- `UnauthorizedTicketActionException`

Required concepts:
- Exceptions
- Custom exceptions
- `try`, `catch`, and `finally`
- `Throwable` awareness

Behavior to implement:
- Closing an already closed ticket throws a clear exception.
- Assigning a ticket to an invalid agent throws a clear exception.
- Searching for a missing ticket throws a clear exception.

Completion check:
- The student can explain when to return `null` and when to throw an exception.

---

### Milestone 8 - Static Members, Constants, and Late Static Bindings

**Goal:** Use class-level behavior carefully.

Required concepts:
- Static methods
- Static properties
- Class constants
- `self::` vs. `static::`
- Late static bindings

Possible behavior:
- A base ID generator class with child-specific prefixes.
- Constants for system limits, such as maximum title length.
- Static factory methods for creating ticket IDs or messages.

Completion check:
- The student can explain when static behavior is useful and when it can make testing harder.

---

### Milestone 9 - Object References, Cloning, and Readonly Objects

**Goal:** Prove understanding of object identity and immutable values.

The student must create or use:
- A readonly `TicketId`
- Cloning behavior for safe ticket snapshots

Required concepts:
- Object handles
- Assignment vs. cloning
- `clone`
- `__clone`
- Readonly classes or readonly properties
- Immutability

Behavior to implement:
- Changing one ticket variable affects the same object when it references the same instance.
- Cloning a ticket snapshot prevents accidental changes to the original.
- Ticket IDs cannot be modified after creation.

Completion check:
- The student can explain the difference between equal objects and the same object.

---

### Milestone 10 - Magic Methods, Object Comparison, and Serialization

**Goal:** Use PHP object behavior intentionally.

Required concepts:
- `__toString`
- `__get` or `__set` only if there is a clear reason
- `__serialize` and `__unserialize`
- `==` vs. `===`
- Object serialization risks

Behavior to implement:
- `Ticket` can be converted to a short readable string.
- Ticket export does not leak internal-only notes unless explicitly allowed.
- The student can compare two tickets and explain the result.

Completion check:
- The student can explain why magic methods should not hide important behavior.

---

### Milestone 11 - Namespaces, Autoloading, and File Storage

**Goal:** Turn separate files into a small organized application.

Required concepts:
- Namespaces
- `use`
- PSR-4 style autoloading
- `spl_autoload_register` or Composer autoloading

Behavior to implement:
- Classes live in matching folders and namespaces.
- The app can run from `playground.php`.
- `FileTicketRepository` can save and load ticket data from a file.

Completion check:
- The student can map a namespace like `App\Domain\Tickets\Ticket` to its file path.

---

### Milestone 12 - Attributes, Anonymous Classes, Object Iteration, and Lazy Objects

**Goal:** Touch the advanced features in a realistic but small way.

Required concepts:
- Attributes
- Anonymous classes
- Object iteration
- Lazy objects or lazy initialization

Possible behavior:
- Mark sensitive fields with a `Sensitive` attribute.
- Mark important service methods with an `AuditAction` attribute.
- Use an anonymous notifier in one manual test.
- Make file storage initialize lazily only when first used.
- Make a ticket collection iterable.

Completion check:
- The student can explain which advanced features added value and which ones should not be overused.

---

### Milestone 13 - Testing

**Goal:** Prove the project works with focused tests.

Required concepts:
- PHPUnit
- Assertions
- Testing exceptions
- Testing classes through public behavior

Minimum tests:
- A ticket can be created with valid data.
- Empty ticket title is rejected.
- Ticket status transitions work correctly.
- Invalid ticket transition throws an exception.
- `TicketService` works with an in-memory repository.
- A missing ticket throws `TicketNotFoundException`.

Completion check:
- The student can explain what each test protects from breaking later.

---

### Milestone 14 - Final Review

**Goal:** Prove understanding, not only working code.

The student must write `notes.md` with answers to:
- What are the most important classes in the project?
- Where did you use encapsulation?
- Where did you use polymorphism?
- Where did you use inheritance, and why was it justified?
- Which interface made the project easier to change?
- Which exception represents a real business failure?
- Which enum prevented invalid data?
- Which class was easiest to test, and why?
- What would you improve if this became a real production project?

Completion check:
- The student can explain the whole project from memory.
- The student can answer interview-style questions about every major design choice.

---

## Concept Coverage Checklist

Use this checklist at the end. The project is complete only when every item is covered by real code or a clear written explanation in `notes.md`.

```
Lecture 01 - Why OOP is useful in growing PHP projects
Lecture 02 - Classes and objects
Lecture 03 - Properties
Lecture 04 - Methods and $this
Lecture 05 - Constructor and constructor promotion
Lecture 06 - Visibility
Lecture 07 - Encapsulation
Lecture 08 - Property hooks
Lecture 09 - Asymmetric visibility
Lecture 10 - Inheritance
Lecture 11 - Method overriding and parent::
Lecture 12 - Static members and class constants
Lecture 13 - Abstract classes
Lecture 14 - Interfaces
Lecture 15 - Polymorphism
Lecture 16 - Type declarations and return types
Lecture 17 - Covariance and contravariance
Lecture 18 - Traits
Lecture 19 - Magic methods
Lecture 20 - Object references
Lecture 21 - Final and cloning
Lecture 22 - Readonly and immutability
Lecture 23 - Namespaces and autoloading
Lecture 24 - Enums
Lecture 25 - Exceptions
Lecture 26 - Attributes
Lecture 27 - Anonymous classes and object iteration
Lecture 28 - Lazy objects or lazy initialization
Lecture 29 - Late static bindings, comparison, and serialization
Lecture 30 - End-to-end mini-project thinking
Lecture 31 - PHPUnit testing
Interview Questions 01-42 - Explain every major design choice in interview form
Visual Maps 01-12 - Draw the OOP flows and the end-to-end system before building
```

---

## Mentor Session Flow

Use this flow each time the student works on the final project.

### PLAN

Ask:
- Which milestone are you working on?
- What files did you create or change?
- What behavior should work now?

### DO

The student writes the code in their own files.

The mentor may explain the next step and show small examples in chat, but must not write or save the implementation for the student.

### CHECK

The mentor asks one focused question or gives one small verification task.

Examples:
- "Show me where invalid ticket status is prevented."
- "Which interface lets you replace storage?"
- "What happens if this ticket is already closed?"

### ACT

- If correct: mark the milestone as complete.
- If partially correct: name the missing concept and ask for one focused change.
- If stuck: reduce the task to a smaller version.

---

## Progress

```
Milestone 00 - Project Setup
Milestone 01 - First Objects
Milestone 02 - Encapsulation and Validation
Milestone 03 - Enums and Safe State
Milestone 04 - Inheritance and Shared User Behavior
Milestone 05 - Interfaces and Polymorphism
Milestone 06 - Abstract Classes, Traits, and Reuse
Milestone 07 - Exceptions and Business Rules
Milestone 08 - Static Members, Constants, and Late Static Bindings
Milestone 09 - Object References, Cloning, and Readonly Objects
Milestone 10 - Magic Methods, Object Comparison, and Serialization
Milestone 11 - Namespaces, Autoloading, and File Storage
Milestone 12 - Attributes, Anonymous Classes, Object Iteration, and Lazy Objects
Milestone 13 - Testing
Milestone 14 - Final Review
```

Mark a milestone with ✅ only after the student can explain it and the code behavior works.

---

## Source References

This project is based on the same official learning sources used by the lecture, interview, and visual-maps tracks.

Sources:
- https://www.php.net/manual/en/oop5.intro.php
- https://www.php.net/manual/en/language.oop5.basic.php
- https://www.php.net/manual/en/language.oop5.properties.php
- https://www.php.net/manual/en/language.oop5.decon.php
- https://www.php.net/manual/en/language.oop5.visibility.php
- https://www.php.net/manual/en/language.oop5.property-hooks.php
- https://www.php.net/manual/en/language.oop5.inheritance.php
- https://www.php.net/manual/en/language.oop5.abstract.php
- https://www.php.net/manual/en/language.oop5.interfaces.php
- https://www.php.net/manual/en/language.types.declarations.php
- https://www.php.net/manual/en/language.oop5.variance.php
- https://www.php.net/manual/en/language.oop5.traits.php
- https://www.php.net/manual/en/language.oop5.magic.php
- https://www.php.net/manual/en/language.oop5.references.php
- https://www.php.net/manual/en/language.oop5.final.php
- https://www.php.net/manual/en/language.oop5.cloning.php
- https://www.php.net/manual/en/language.namespaces.php
- https://www.php.net/manual/en/language.enumerations.php
- https://www.php.net/manual/en/language.exceptions.php
- https://www.php.net/manual/en/language.attributes.php
- https://www.php.net/manual/en/language.oop5.anonymous.php
- https://www.php.net/manual/en/language.oop5.lazy-objects.php
- https://www.php.net/manual/en/language.oop5.late-static-bindings.php
- https://www.php.net/manual/en/language.oop5.object-comparison.php
- https://www.php.net/manual/en/language.oop5.serialization.php
- https://docs.phpunit.de/en/12.2/writing-tests-for-phpunit.html
