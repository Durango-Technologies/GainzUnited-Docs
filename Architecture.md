# GainzUnited Architecture Guide

Welcome to the `GainzUnited` Development Team! This document will provide a quick overview of the design behind the app. Note - the app is in need of a refactor, and could use a more reactive approach.  At the time of it's creation, SwiftUI & Combine were relatively new, but future updates would benefit from merging - at the very least - an observable approach in order to avoid 'Callback Hell'.

## Structure
*Services* - contain shared code for firebase
- Intermixed arch - some are singletons (Service.shared.Function-Name) and some are static (just Service.Function-Name)

*Cache Service* - Contains all caches for the app. Saves on calls to db - especially for images.
- We use both 'Core Data' and 'UserData' to persist information on app close

*Database & Storage* - Firebase/Firestore
- 2 databases - **Test** & **Stage/Prod**
- Images stored in Firestore, retrieved via services - plain api call w/ 

*Authentication/Log-in* - FirebaseAuth (Email & Password)

#### Key Files/Folders

*Main.storyboard* - contain the majority of the view controllers
- Avoid for newer/additional content (slow loading & performance in xcode - it's a monolith)
- Instead, write Views separately in an XIB file

*View Controllers* - Store all the VCs of the app, both storyboard referenced and instantiated VCs

*Views* - Contains Cells for TableViews & Views to be instantiated from View controller (mostly to avoid 'main.storyboard')

*Resources* - Images

*Helpers* - `Helpers.swift`
- contains various helper functions that are referenced throughout the app.


