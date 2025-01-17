
Concepts and Use Case
- small part of your app that's discoverable at the moment its needed and lets people complete a quick task
- Invocation -> App Clip Card -> Open App Clip -> Task Completed

Challenges and Solutions
- Technical Limitations
	- Only supports iOS 14+
	- Max size 10MB (iOS 15-)
	- Max size 15MB (iOS 16-)
	- Max size 50MB (iOS 17+) uncompressed
	- Reuse code to keep the same UX
		- Split targets using subspec cocoapods
		- Split shared code using processor macro
	- Install size can be different in App Store -> because code got obsfucated when uploaded to App Store
	- Limited Capabilities:
		- Push notification: 8 hours after use
		- Location access: 1 day, only while in use
		- App Extension: cannot include
		- Face ID: not availabke, TouchID is
		- iCloud: Read only to public iCloud
		- Data sharing: Nom except its full app
	- App Clip will be removed in 30 days after use

- Integration Difficulties
	- limited length for invocation (length is limited)
	- Links: (Safari, Messages, QR Codes)
		- Appclip card will not show in Safari private mode
		- require website's meta tag configuration
		- unexpected issue with www. prefix (just remove www.)
	- Distribution: not possible for enterprise distribution (they have their own link)

- Adoption and Analytics
	- Hard to get stakeholders buy-in
	- Limited tools for tracking user conversions within Apple
		- Cannot track how many people downloaded your AppClip
		- Maybe can use some third party analytics tracker

Innovation @ OKX