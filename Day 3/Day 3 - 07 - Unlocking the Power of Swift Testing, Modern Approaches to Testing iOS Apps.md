Brand new testing specifically for Swift code
Prepared for new languages such as concurrencies, etc
Open source
Works on platforms supported by swift
Swift Testing addresses what XCTest lacks

why Struct instead of Class? -> XCTest needs to inherit
in case from Swift Testing, it doesnt need to inherit anything
Struct is faster

now we use @Test, and no need to use test on function name

Now we use #expect macro instead of XCTAssert -> no need to remember the assert class name anymore

Can now add custom name instead of function name
@Test("search user by user name")
func ...

Trait -> label to clarify what the test is actually about
- .disable
- .enabled
- etc...

@Suite

@Tag -> create your own set of custom tag
Tags can be shown to only test those that got tagged

Parameterized Testing
- add parameters to our testing functions so that we can test easily based on certain scenario
- @Test("", arguments: [("user A", 1), ("user B", 2)])

What to be mindful about in Testing
- Integrating it gradually on legacy codebases
- Ensure the team is familiar with the syntax
- Maintain test coverage while avoiding test duplication
- Leverage swift testing for unit and functional testing

