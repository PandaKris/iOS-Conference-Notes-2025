Typical dev workflow

Onboard -> Analyze -> [Implement -> Verify -> Iterate -> Implement]

Annual developer survey -> build time concerns
- Memory Requirements actually got bigger while build time gets smaller

Observation from other platform
	- Jetpack Compose
	- React Hot Reloading

How to tackle
- Modularization (Decoupling everything)
	- Risk: Refactoring across the codebase
	- Effort: Balancing feature delivery with modularization
	- Doesn't know if it will be enough

- Design:
  Application Layer (Application)
  Feature Layer (Posts List, Post Detail, Settings)
  Capability Layer (Networking)
  Core Layer (Shared Model)

Do we need to build everything? or just pre-build some?
- Binary Caching
	- Find modules that doesnt need to be changed / rarely change, exclude it from build


