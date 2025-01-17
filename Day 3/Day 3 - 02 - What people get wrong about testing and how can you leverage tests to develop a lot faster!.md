
Why Testing is Valuable
- why only so few apps in swift have tests?
	- dont find testing valuable
	- need to rush for features
	- can add it later
	- code is simple, no need for a test
- often time people think testing is for big teams
	- the smaller the team, the bigger the win
		- large teams have QA, we dont

TDD
- we write test before we write the code
- help capture issues early in development
- Rhythm
	- Red: Make it fail
	- Green: Make it pass
	- Refactor: Iterate/Improve
	- Repeat

Anti-patterns in testing
- Testing Implementation Detail
	- implementation that needs database / userdefaults / etc
	- none of that matters on testing
	- instead, create a behavioral test (test can still work if you change database)
- Flaky Tests
	- tests that pass and fail intermittenly without any changes to the code
		- sometime it works, sometime it fails
		- it wastes a lot of time fixing bugs that arent really bugs
	- can be solved with proper dependency injection
	- use a mock, create a controlled environment on your test
- Fragile Tests
	- Tests that break easily with any changes in the codebase
		- Writing tests that are extremely specific

Best practices
- Treat your test the same care as your production code
- 3A (Arrange, Act, Assert) / Given When Then
- One Side-Effect per Test (Focused Testing)
	- Design tests to verify a single aspect / concern
	- rather than a big test function, split it to 5 different test function
- Test the behavior, not implementation
	- Focus on what it does, rather than how it does it
- Behavior Testing
- Isolate Tests
	- Each test should run independently
	- Avoid shared state between tests (setUp, tearDown)
	- Each test should start fresh
- Use Meaningful Function Names
	- When you read the logs later,
		- format: test_addingItemToCard_increaseCount()
- Keep Tests Fast
	- Mock expensive operations
	- Benefits: Faster CI

Snapshow Tests
- Capture a view or data structure and compare with the correct image
- Use Point-Free Library
- Visual Changes shown in git diff

UI/Integration with XCUITest
- Simulate user interactions
- Test the integration of multiple components
- Help verifies the outcome, but its not the best way to do it
	- everytime we change the implementation detail, all the test need to change
	- Create Page Object Pattern to abstract design from the design of the UI
- Can still be pretty flaky because its running everything

Introducing Testing in Legacy Codebases
- Need a gradual approach in testing, no one's gonna freeze development for 2 months
- Identify critical paths for your project, prioritize testing efforts on those key functionality
- Incremental testing approach
- Use test as a way to refactor safely
- Create a protocol to help mocking
- Approval Testing for Existing Behavior
- Gradual Refactoring with Tests

Tools and Libraries:
- Difference or CustomDump
- Sourcery / SwiftyMocky
- SwiftMock / Mockable
- Swift-Dependencies

Conclusion:
- Testing is crucial for long-term efficiency and code quality
- Focus on behavior, not implementation detail
- Focused and fast isolated test, no need to cover everything
- If you have legacy codebases, do it gradually
- When you work on new features, write tests first to make life easier

https://x.com/merowing_