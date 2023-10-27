---
{"dg-publish":true,"permalink":"/zettelkasten/android-gradle/","title":"Gradle","tags":["status/todo","core/tech/android"],"noteIcon":"","created":"2023-10-25T17:28:26.387+01:00","updated":"2023-10-25T17:48:34.802+01:00"}
---


# Gradle

Gradle is a **build automation** for android development; It takes all the project configuration to generate an `APK` . 

---
#### Ways to define gradle files
Gradle groovy
Gradle Kotlin

---

#### Gradle files

##### `build.gradle (project)`
- You can have more of this if you have a multi-module project
- Contains configuration about the project

##### `build.gradle (:app)`
- Android compile configurations

##### Build Types
It allows you to handle configurations for different app lifecycles i.e a `develop` or `release` versions. This can set environment varaibles and configurations.

```
buildTypes {
	release {
		minifyEnabled true
		applicationIdSuffix ".release"
	}
	custom {
	}
}
```

###### Product  flavour
Allows you to overwrite app configurations and it mixes with the build types, so if you have a `debug,release` build types and you want to create a version of the app that uses a top-level sdk version without leaving support for an older API you can create a flavour, so you'll end up with:
- `minSDK30Debug`
- `minSDK30Release`
- `minSDK21Debug`
- `minSDK21Release`

##### `gradlew`
Gradle `w`rapper which is an executable file that contains **tasks**, this means that you can use that file to run tasks that you use on your IDE i.e:

```
./gradlew build
./gradlew tasks
```

### Variables


### Dependency management


## Relates to
## References
