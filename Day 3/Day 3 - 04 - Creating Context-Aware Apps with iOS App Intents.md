
Is there any they can use app functionality without having being in our app (expose my app functionality outside the app)

Apple introduced AppIntents in iOS 16
- Utilizing Spotlight, Shortcuts, Siri, and Apple Intelligence, without having to go into the app

Building Blocks
- Intent: the action that we want to perform
- Entity: a noun, the event
- Shortcuts: Combines Intent and Entity to perform and give it to the user
- AppIntent is a protocol
	- provide title
	- provide perform() method, main part of what will actually happen
		- case study: perform gets calory and return a form of dialog
	- openAppWhenRun -> when set to true, will open the app, can also modify where we want to go from perform() method

How to develop App Intents

Indexing App Entities

Enhance the existing intents to support Apple Intelligence and Siri
	Exposing it to Apple Intelligence?
	- @AssistantEntity(schema: .journal.entry) -> put this in journal type schema for Apple Intelligence

