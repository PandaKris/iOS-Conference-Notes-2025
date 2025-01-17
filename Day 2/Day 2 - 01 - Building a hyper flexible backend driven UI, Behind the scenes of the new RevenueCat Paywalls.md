
BTS of RevenueCat app

How they build their hyper flexible backend driven UI
- Changes from Backend will apply to the SwiftUI FE
- Why we use backend driven UI?
	- Change the UI without needing an app update
	- No need to wait on app review or users to update the app
	- Non-engineers can make changes
	- Send different UI's to different users based on backend context
		- Usually for A/B tests to experiment with different layouts
		- Different layout based on user's preference

Gradient of Backend Driven UI (Maintainability <------> Flexibility)
- 1st gradient, just pick layout A or B
- 2nd gradient, create components (Headers, Body, Reviews, etc)
- 3rd Gradient, each item (Text, Icon, etc)

RevenueCat -> in-app purchases made easy
- SDK -> show in-app purchase on your app
- Handle the pain of talking to StoreKit

**Paywall V1 Architecture**
RevenueCat Backend -> Paywall Json file (color, images, backgrounds, display_restore_purchase = true, localized strings)  -> App

Big pain in designing something like this: Backwards compatibility
- When we make template 4, turns out the template doesnt update their ios version yet

**Paywall V2 Architecture**
- Main goals:
	- More templates
	- More flexibility within those template
	- They don't want a new template with new action, they want to customize it themselves
	- Then we need to go to Gradient 3

- RevenueCat Backend -> JSON file `[Component(), Component(), Component(), Component([Component()]), ...`

- Steps in SDK
	- Deserialize JSON into Swift objects -> Traverse the whole component tree -> Convert decoded objects to view models.
		- If not valid -> Render backup paywall, 
		- if valid -> Render layout component one by one

Biggest Challenge: Backwards Compatibility
- Web API Version -> App (SDK Version) -> iOS Version (user)

Backwards Compatibility Approach
- Try to create everything with the core building block components
- Component Fallbacks
	- If it runs into a component it doesnt know about, the renderer checks for a fallback component and renders that instead
- Fallback Paywalls (back to default, ask developer to upgrade SDK)