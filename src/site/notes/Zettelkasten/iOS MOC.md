---
{"dg-publish":true,"permalink":"/zettelkasten/i-os-moc/","title":"iOS | Map Of Content","tags":["core/tech/ios","status/todo","status/MOC"],"created":"2022-10-06T10:58:29.612+01:00"}
---


# Map of Contents: iOS 
## Porqué?
Lo que aprendas para desarrollar en IOS, no solo te servirá para desarrollo mobil; también te servirá para desarrollar en todo el [[Zettelkasten/Apple Ecosystem\|Apple Ecosystem]] (Watch, iPad, Mac, iPhone)


### Porque no escoger desarrollo en iOS
- Si tienes una app en mente y quieres que este disponible mas de una plataforma (android & ios) podrias aprender [[Zettelkasten/React Native\|React Native]] o [[Flutter\|Flutter]] 
- Si no quieres que tu idea este atada a la app store podrias hacer una [[Web app\|Web app]] 
- Si no quieres gastar dinero al publicar tu app

---

También es importante saber [[Zettelkasten/How does an app work\|How does an app work]], y en *cuales son sus diferencias con [[Zettelkasten/Web development MOC\|Web development MOC]]* u otros tipos de desarrollo, como [[Zettelkasten/Internet of Things MOC\|Internet of Things MOC]], esto porque ==es importante saber con qué herramientas contamos para solucionar un problema== ya que hay veces que lo que nuestra area de expertiz no siempre es la *mejor herramienta para el problema*. 
Muy bien! Una vez ya sabemos porqué el desarrollo iOS es importante y tenemos noción de qué tipo de problemas podemos solucionar vamos a comenzar...

--

> [!NOTE]- Referencias
> - [[Zettelkasten/Apple Ecosystem\|Apple Ecosystem]]
> - [[Zettelkasten/How does an app work\|How does an app work]]
> - [[Zettelkasten/Web development MOC\|Web development MOC]]
> - [[Zettelkasten/How to be a better developer\|How to be a better developer]]

---

## Lo Básico 

--

Antes de comenzar a programar, debemos conocer nuestra herramienta; [[Zettelkasten/XCode\|XCode]] con ella trabajaremos durante toda nuestra travesía, así que vale la pena tomar un bootcamp de como es que funciona y sentirnos cómodos con la interfaz.

Una vez conocemos la interfaz podemos empezar a programar, y esto lo haremos con el lenguaje de programación llamado [[Zettelkasten/Swift\|Swift]], el cual es un lenguaje desarrollado por Apple para el propósito de desarrollar Apps nativas. Pero es importante notar que ==los principales lenguajes de programación para el desarrollo mobil en iOS son [[Zettelkasten/Objective-C\|Objective-C]]y [[Zettelkasten/Swift\|Swift]]==. Este primero era el **principal lenguaje** hasta la introducción de Swift en ==2014==. 

--

> [!NOTE]- Referencias
> - [[Zettelkasten/Swift\|Swift]]
> - [[Zettelkasten/XCode\|XCode]]
> - [[Zettelkasten/Objective-C\|Objective-C]]

-- 
### Conceptos & Frameworks
##### Bundle ID 
**uniquely identifies an application in Apple's ecosystem**. This means that no two applications can have the same bundle identifier. To avoid conflicts, Apple encourages developers to use reverse domain name notation for choosing an application's bundle identifier `com.feernandooff.MY_APP`

##### Plist
A plist or property list is **an XML file containing data in form of key-value pairs**
`Project-> (Targer) -> Info`

##### Package managers
- (Cocoapods/Swift package manager)
- [[Zettelkasten/Swift Libraries\|Swift Libraries]]


---

## Construyendo una app
Una vez que ya sabemos movernos por XCode y podemos hacer programas básicos, estamos listos para comenzar a hacer una app. Y nos encontraremos con una decision bastante importante: ==que librería de UI utilizaremos?==. 

> [!NOTE]- Diferentes formas de construir una app
>1. **Storyboards**: Storyboards are a visual way to design and lay out the UI of an iOS app. They allow you to create a sequence of screens and define the flow between them. 
>
>3. Interface Builder: Interface Builder is a graphical tool that allows you to design and configure the UI of an iOS app. It provides a drag-and-drop interface for adding UI elements to your app. 
>
>4. **UIKit**: UI elements can be created programmatically using Swift or Objective-C code. This approach is useful for creating dynamic UIs or when the layout needs to be generated at runtime. 
>
>5. **SwiftUI**: SwiftUI is a modern UI framework for iOS that allows developers to build UI using a declarative programming model. It simplifies the UI development process and provides a more efficient way to build UI for iOS apps. 
>
>6. **Cross-platform frameworks:** Cross-platform frameworks such as React Native, Flutter, and Xamarin can also be used to build UI for iOS apps. These frameworks allow developers to build UI using a single codebase that can be deployed to multiple platforms. 

### [[Zettelkasten/Swift UI\|Swift UI]]
- Example of a UI using swiftUI
```swift
struct ContentView: View {
	var body: some View {
		VStack {
			HStack {
				Text("Helllo world")
				Image(systemName: "home")
			}
			Button("Click here")
		}
	}
}
```
### [[Zettelkasten/iOS Storyboards\|iOS Storyboards]]
- Example of a UI using Storyboards
*Image + Code*

---

### Folder structure
- [[Zettelkasten/iOS Folder Structure\|iOS Folder Structure]]
### Design Patterns
- [[Zettelkasten/MVVM\|MVVM]]
1. Model-View-Controller ([[Zettelkasten/MVC\|MVC]]): MVC is a software architecture pattern that separates an app into three interconnected components: the model, the view, and the controller. It is a popular pattern in iOS development and is used to organize code and separate concerns.

2. [[Zettelkasten/Delegate Pattern\|Delegate Pattern]] : Delegation is a design pattern that allows one object to delegate tasks to another object. It is commonly used in iOS development for handling user interactions and events.

3. [[Observer Pattern\|Observer Pattern]] : Observer is a design pattern that allows one object to observe changes in another object. It is commonly used in iOS development for handling notifications and updates.

4. [[Zettelkasten/Singleton Pattern\|Singleton Pattern]] : Singleton is a design pattern that allows only one instance of a class to be created and provides a global point of access to that instance. It is commonly used in iOS development for managing global application state.

5. Factory: Factory is a design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created. It is commonly used in iOS development for creating objects with complex initialization requirements.

6. Strategy: Strategy is a design pattern that allows algorithms to be selected at runtime. It is commonly used in iOS development for implementing different behaviors or algorithms depending on user input or other factors.
---


## Probando nuestra app (Testing)

---

## Publicando nuestra app (Publishing)

---
## Avanzado
### Variables de entorno (Env vars)
### Debugging  
### Pagos (Payments)
- AppStore SDK
- [[RevenueCat\|RevenueCat]]
### Analíticas (Analytics)
### Internacionalización (Internationalisation)
### Accesibilidad (Accessibility)

- [[Zettelkasten/Apple Certificates\|Apple Certificates]]


## Analíticas