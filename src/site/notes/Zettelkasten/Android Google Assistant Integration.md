---
{"dg-publish":true,"permalink":"/zettelkasten/android-google-assistant-integration/","title":"Android Google Assistant Integration","tags":["status/todo","core/tech/android"],"noteIcon":"","created":"2023-10-20T17:05:25.460+01:00"}
---


# Android Google Assistant Integration

The app actions allow the user **launch certain functionallity** of your app from outside of it, there among them:
- Google **Assistant**
- App Hovering Shortcut

> [!warning] Google Assistant only works on Google Play

### Terminology
- shortcuts
- capability
- [built-in intent (BII)](https://developer.android.com/reference/app-actions/built-in-intents)
- Dynamic Shortcuts
- Static shortcuts

### Quick Start

> [!alert] Prerequisites
> - Same google account in Android Studio and your test Device

#### 1. Create a `xml/shortcuts.xml`

Start by creating a `shortcuts.xml` file inside the `xml` folder.

#### 2. Link the Shortcuts to your Manifest

You have to let the Android OS know that you have shortcuts and capabilities on your app by linking it in the `AndroidManifest.xml`
```xml
<activity ..>
...
<meta-data  
        android:name="android.app.shortcuts"  
        android:resource="@xml/shortcuts" />
...
</activity> 
```

#### 3. Create a shortcut
To make a shortcut available to the OS and therefore client-facing when holding the app icon.
```xml
<shortcut  
        android:shortcutId="created_matches"  
        android:icon="@mipmap/ic_launcher"  
        android:shortcutShortLabel="@string/shortcut_open_match"  
        android:enabled="true">  
    <intent  // Intent called once the user presses the button
            android:action="android.intent.action.VIEW"  
            android:targetPackage="com.tapadoo.example" 
            android:targetClass="com.tapadoo.example.MAIN" />   
</shortcut>
```
#### 4. Create an Assistant Capability
You can choose any of the [pre-build intents](https://developer.android.com/reference/app-actions/built-in-intents/bii-index) and assing any of the exposed variables to the intent, you can customise the name that you pass to it.

```xml
<capability android:name="actions.intent.OPEN_APP_FEATURE">  
    <intent  
            android:action="android.intent.action.VIEW"  
            android:targetPackage="com.tapadoo.gaamatchtracker"  
            android:targetClass="com.tapadoo.test.MatchActivity">  
        <parameter  
                android:name="feature"  
                android:key="feature" />  
    </intent>  
</capability>
```

#### 5. Inline Inventory

## Relates to
## References
