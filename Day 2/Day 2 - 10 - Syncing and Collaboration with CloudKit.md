Basic
- in database : row -> table -> database
- in cloudkit: ckrecord -> ckrecordzone -> ckdatabase

- CKRecord (it holds key and value)
	- Record ID ("Task")
	- Record Type ("int")

- CKRecordZone
	- Zone Name
		- Default
		- Custom
	- Owner Name

- CKDatabase
	- Public, Private, Shared

- Contained inside a CKContainer

Syncing

Fetching

Subscriptions

Sharing
- CKShare -> save the share -> present the share with UICloudSharingController

Cool Stuff
- Whats good about CloudKit -> No Auth needed, it uses Apple ID already logged in
- CKSyncEngine
- Mark your records as Sortable/Queryable/Indexable
- Deploy Schema Changes <- careful with this. None of your deployment is irreversible
- Private and shared has the most feature, Public has limited features


Github repo check @mufasayc
https://github.com/mufasayc

https://github.com/mufasaYC/Bad-Habits