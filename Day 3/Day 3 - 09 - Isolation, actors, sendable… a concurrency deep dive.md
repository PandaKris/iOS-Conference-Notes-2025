
- Async/Await Syntax
- Structured Concurrency
- Data Race Protection

3 Pillars of Data Race Protection -> these are very closely related
- Isolation
- Actors
- Sendability

Need to understand the compiler's perspective

Actors -> Protect their mutable state from data races

Back then we use these to protect states:
- Locks, DispatchQueue, Semaphores

when data race happens: EXC_BAD_ACCESS

Actors make sure you dont have data races, compiler makes sure its all synchronized.

Actor terminology
- Actor mailbox
	- Actor only does one thing at a time
	- 
- Actor reentrancy
	- Once Actor is waiting for something (Network call), it can run another one

- Actor isolation
	- Actor wants to hold an object to its own
	- So how do we send data to an isolated Actor
	- In Swift Concurrency code is either isolated to an actor or non-isolated
	- Object and states that exists within the same isolation context can be accessed freely
	- Passing object of state between isolation context can only be done under ...
	- When we pass the data, its called isolation boundary
	- Task can inherit a current isolation Context
