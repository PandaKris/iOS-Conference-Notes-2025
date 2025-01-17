2 kinds of functions
- Pure Functions
	- don't depend on / mutate any external state
	- may depend on arguments and local variables
	- may depend on other pure functions
	- for the same input, pure function produces the same output
	- enable equational reasoning
	- easy and fun to test
	- idempotent and retryable (can call the function multiple times)
	- can be cached / memoized
	- can be parallelized


- Effectful Function
	- depend on / mutate external state
`
```
var history: [String]

func multiply(_ x: Int, _ y: Int) -> Int {
	history.append("\(x) * \(y)") <-- side effect! mutates history
	return x*y
}
```
`
- Examples: Disk I/O (CoreData, etc), Networking, Randomness, etc.

Pure functions are restrictive and limited on how we use it, Effectful are powerful and useful

Is it possible to have best of both world?

2 Approaches
- Scenario (Guess a number from 1 to 5) -> Incorrect/Correct -> Continue?

Approach 1: Divide and Conquer
- Programs combine Logic and Effects 
	- Separate Effects and Logic
	- Pure functions now can be tested on its own.
	- But how to test effects?
		- Dependency Injection -> Side Effects injection
			- create protocols


Approach 2: Effect Descriptors
- Program describes the effect it wants to perform
	- create a Effect object and returns it so that the caller will handle it on its own

- 2 style of programming
	- Direct style
	- Continuation-passing style -> completion handler

indirect enum

![[WhatsApp Image 2025-01-16 at 11.22.45.jpeg]]

Bridging between direct - continuation passing style

CheckedContinuation

Recap:
- use divide and conquer to pick low-hanging fruits
- use DI for decent side effect control, but be ready to bare the weight of mock-based testing
- if you want to up your side effect control game, explore these topics:
	- Effect descriptors (DSL + Interpreters)
	- Monads (Effect containers)
	- Tagless final
	- Functional Core / Imperative SHell
	- Explore architecture like Redux