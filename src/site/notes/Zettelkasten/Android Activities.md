---
{"dg-publish":true,"permalink":"/zettelkasten/android-activities/","title":"Activities","tags":["core/tech/android","status/done"],"created":"2023-10-11T16:29:38.628+01:00"}
---


# Activities


The Activity class is a Building Block of the Android apps. Unlike other paradigms, the launching point is not a `main()` function, instead is a `MainActivity` class and is initialised with specific [[callbacks\|callbacks]]  methods that correspond to specific stages of its [[Zettelkasten/Android Activities#Lifecycle\|#Lifecycle]].

## Why Activities

The concept of an Activity comes from the different way that a mobile app is used from a desktop app. In which the user can land into your app in different ways i.e; Tapping on the app should open the Home, but tapping into a link that opens someone's profile should show a different screen, meaning, a different activity. The `Activity` class was created to allow this kind of workflows.


> [!info] Activities characteristics
> - An activity serves an an **entry point** for an app's interaction with the user
> - An activity provides **the window** in which the app draws the UI, this can fit the screen or be smaller
> - Each activity can call another activity
> - If you want an activity to be accessible form other apps you have to declare it into the Manifest

## Lifecycle
> For more information see [[Zettelkasten/Android Activity Lifecycle\|Android Activity Lifecycle]]

### Declaring activities

All the usable Activities in your app **must be registered** in the `AndroidManifest`, weather you want to navigate from one activity to another, allow that activity to be launched from other apps or your app launch another app.

### Basic Navigation
You can navigate with intents as follows:
```java
Intent intent = new Intent(this, TargetActivity.class);
startActivity(intent);

```



## Relates to
## References
