Based on true story
- a tamagochi pet app, suddenly after 8 months, the data is gone
- turns out if you open live activity, reboot, all the data is gone
- UserDefaults suddenly turning nil

UserDefaults losing its keys and value when phone is rebooted
- before phone unlock (nil)
- after phone unlock (item found)

UserDefaults is very old (1994)

isProtectedDataAvailable -> only available on the main app, not widgets, live activities, etc.
lock screen widgets
- unavailable in app extensions

Apple gives update that increase app launch performance
- Application Prewarming (apple will prelaunch an app based on their behavior)
- prewarming can call **willFinishLaunchingWithOptions** and **didFinishLaunchingWithOptions**
- sample scenario (streak app)
	- appDidFinishLaunching -> add streak
	- when prelaunched, userdefaults will be nil

`UIApplication.protectedDataDidBecomeAvailableNotification`

Tips:
- use App Groups (to be able to use data for widgets activities etc)
- threading, make sure multiple people cant get to this one task (only one person touching the data at any point) - dispatchQueue sync
- NSFileCoordinator -> help to make sure if widgets / live activities are touching the data at the same time
- TinyStorageKey (if key has typo it will send compiler error)

https://github.com/christianselig/TinyStorage