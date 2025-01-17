
What is a good code
- Maintainable
- Testable
- Good Performance

"Thoughtful Code" - when you can sit down to think about what you write, and solve it the best way you can

But you dont have too much time for that, new features need to be added, new sprint backlogs, new WWDC videos, we cant slow down

--------------
Today's Goal: Write Thoughtful Code

Polishing code
- can it run faster, can it be clearer, can it be simple, can it be more consistent?

"You only know what good code looks like when you look at many bad codes"


Workshop
- Xcode can now understand camel case spell checking
- Hash Collision Attack -> check it
- count replace to isEmpty -> checking using count is slower (because it has to count (O(n))) while isEmpty is just simple boolean check ![[Screenshot 2025-01-15 at 09.53.10.png]]
- ! -> can still be fine if its part of your own error (you need to type it correctly)
	- example: "view controller names, if you type it wrong then just change it", "wrong url, just change it"
- `Hashable` is a sub protocol of `Equatable`, so there's no need to conform both simultaneously
- Documenting with ///
- AssetCatalog instead of Color(red: xxx, green: xxx, blue: xxx)
- Semantic naming: naming as what it does instead of what it looks like (instead of brown, say "tabBackground"
- PersonNameComponents -> it'll figure out how to best display the name based on the locality
- AsyncImage -> sometimes can show grey image and wont try again. use something like this
````swift
 AsyncImage(url: person.thumbnail, scale: 3) { phase in
                        if let image = phase.image {
                            image.resizable()
                        } else if phase.error != nil {
                            Image(systemName: "person.circle")
                        } else {
                            ProgressView()
                        }
                    }
````

- .localizedStandardContains(string)![[Screenshot 2025-01-15 at 11.34.47.png]]
- refreshable {}



Paul Hudson's Format:
- Lecture on what is a good code
- Importance on Thoughtful Code
- Exercise by giving a case study (app project)
	- Give 10 minutes for learners to see the project
	- They will see any issues and write down what it is and how they can do better
- Rest of the Activity:
	- Run through the submission, talk it out and fix the code together
	- Talk about the changes and why it can be better this way
- `Text("Select ^[\(viewModel.selectedPeople.count) people](inflect: true)")`
- 