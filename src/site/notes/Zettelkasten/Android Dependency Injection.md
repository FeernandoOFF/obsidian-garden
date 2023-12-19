---
{"dg-publish":true,"permalink":"/zettelkasten/android-dependency-injection/","title":"Hilt","tags":["status/todo","core/tech/android"],"created":"2023-11-30T15:13:15.786+00:00"}
---


# Dependency Injection with Android

### Introduction

Dependency injection is one of the ways to achieve [[Zettelkasten/Clean Architecture\|Clean Architecture]] by abstracting dependencies and by doing so make the code less coupled, which means easier modularisation.

Google has helped to create open-source tools that allow an easier management of dependencies.

#### Dagger

Google has created **dagger** which is a dependency injection tool for **java and kotlin**.

#### Hilt

Hilt is a dependency injection library for **Android apps**, which under the hood uses Dagger, thus simplifying the setup and reducing boiler plate.


## Guide


```kotlin
@Module
```


This annotation tells Hilt that this class contributes to dependency injection object graph.

```kotlin
\_@InstallIn(SingletonComponent::class)
```

This annotation tells Hilt that the dependencies provided via this module shall stay alive as long as application is running.

```
@Provides
```

This annotation marks the method `provideChannelDao` as a provider of _ChannelDao_.

Now Hilt knows how to create an instance of _ChannelDao_ but to create such an instance, Hilt needs to know how to create an instance of _AppDatabase._ For that add another method below provideChannelDao.


```
@Provides  
@Singleton  
fun provideAppDatabase(@ApplicationContext appContext: Context): AppDatabase {  
    return Room.databaseBuilder(  
        appContext,  
        AppDatabase::class._java_,  
        "RssReader"  
    ).build()  
}
```


There are two things to note here.

1. **@Singleton** annotation tells Hilt that AppDatabase should be initialized only once. And the same instance should be provided every time it’s needed to be injected.
2. **@ApplicationContext** allows hilt to provide application context without having to explicitly specify how to obtain it.


HilAll Hilt apps must have an `Application` class that is annotated with `@HiltAndroidApp` .

```kotlin
@HiltAndroidApp
class MainActivity: Application(){

}
```

## Relates to

[Using room database with Hilt](https://svvashishtha.medium.com/using-room-with-hilt-cb57a1bc32f)
## References
