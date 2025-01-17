
https://donnyplus.com

Goals:
- Reiterate Concurrency's Foundations
- Gain better understanding of Sendable
- Learn about actors
- Practice new skills
- Learn how to prepare for Swift 6


From closure to async await
- From a weird "move to the other code then go back here", now async can be a single line

- Child task is not task inside task
- Child task is for example, a TaskGroup -> can add task inside it
	- TaskGroup is the parent task, cannot return until all child task completes -> Structured Concurrency
- Another example of child task -> async let
- Anything else other than that is detached / unstructured Tasks
- Difference between async let and TaskGroup
- for await _ in group {

Structured concurrency is very different from GCD

How to protect/prevent data race
- Actors and Sendability

Guides / can check for isolated actors
- @preconcurrency

Actor Reentrancy


Rule of thumb in swift concurrency:
- Do not lock / block a thread

nonisolated

Sendable protocol
- promises the object will not be subject to data races

@unchecked Sendable -> bypasses the promises
- use this when you really know the object is thread safe
- no other way that makes sense
- you want to revisit the concurrency later

@Sendable

https://donnywals.notion.site/Swift-Concurrency-iOSConfSG-179d51b1b67f80acb011e5c6b14b31e6

