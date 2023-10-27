---
{"dg-publish":true,"permalink":"/zettelkasten/android-fragments/","title":"Fragments","tags":["status/todo","core/tech/android"],"noteIcon":"","created":"2023-10-11T17:40:12.580+01:00","updated":"2023-10-18T14:37:01.102+01:00"}
---


# Fragments


A Fragment is like a `Component` , which is a portion of UI that encapsulates his own layout, lifecycle and events. This opens the door for **Modularity** ( like [[Zettelkasten/Component Composition\|Component Composition]] in web frameworks)

#### Characteristics
- Fragments have to be **hosted by an activity** or other fragments. 
- Fragments are also easier to Create/Distroy - navigation?
- While your activity is in the `STARTED` [[Zettelkasten/Android Activity Lifecycle\|Android Lifecycle]] or higher, fragments can be added, replaced, or removed. And you can keep a record of these changes in a back stack that is managed by the activity, so that the changes can be reversed.


> [!NOTE] Some [[Android Libraries\|Android Libraries]] use Fragments as they core.


### Using a fragment
> You'll need to install the [AndroidX Fragment library](https://developer.android.com/jetpack/androidx/releases/fragment) 

```kotlin
class ExampleFragment : Fragment(R.layout.example_fragment)
```
#### Add a Fragment to an activity

You fragment **must be embedded** within an AndroidX FragmentActivity - which is the base class for for `AppCompatActivity`. You'll need to add a `FragmentContainerView` in which you can add a Fragment in two ways:

- Via XML layout
```xml
<!-- res/layout/example_activity.xml --><androidx.fragment.app.FragmentContainerView
	xmlns:android="http://schemas.android.com/apk/res/android" 
	android:id="@+id/fragment_container_view"   
	android:layout_width="match_parent"   
	android:layout_height="match_parent" 
	android:name="com.example.ExampleFragment"  <!-- This is Your Fragment -->
	/>
```

- Programatically
```kotlin
class ExampleActivity : AppCompatActivity(R.layout.example_activity) {    override fun onCreate(savedInstanceState: Bundle?) {        super.onCreate(savedInstanceState)        if (savedInstanceState == null) {            supportFragmentManager.commit {                setReorderingAllowed(true)                add<ExampleFragment>(R.id.fragment_container_view)            }        }    }  
}
```




### Lifecycle
Every Fragment has their own **lifecycle**  which as the user interacts, the fragment changes lifecycle, thus allowing you to i.e:
- Display the user location when a fragment is presented
- Show the user camera in the screen.
This examples can be done using a `lifecylce-aware component` that can automatically start listening when the fragment becomes active.

#### Accessing the lifecycle
There are multiple ways to get the fragment's lifecycle like, see [[Zettelkasten/Android Activity Lifecycle\|Android Lifecycle]]



### Receive props & Sharing data

> [!warning] Make sure to properly read this
> This is a core idea of the **modularity** so make sure to understand this concept
> You can read the documentation for this [here](https://developer.android.com/guide/fragments/communicate)
> Mistakenly using this concepts can lead to [[Memory Leak\|Memory Leak]]

To enable the proper use of modularisation, the components have to be **isolated** and have a proper **communication channel** to react and share state information. This can be done in different ways.

#### Shared ViewModel with an Activity

A `viewModel` is a ideal choice when you need to share data between multiple fragments and their host activity.
Both your `fragments` and your host activity can use a [[Zettelkasten/Singleton Pattern\|Shared Instance]] of a `viewModel` with an **activity  scope** by passing the activity into the `viewModelProvider` - which instantiates the viewModel or retrieves it if already exists.


```kotlin
class MainActivity : AppCompatActivity() {
// Using the viewModels() Kotlin property delegate from the activity-ktx 
// artifact to retrieve the ViewModel in the activity scope.    
private val viewModel: ItemViewModel by viewModels()
override fun onCreate(savedInstanceState: Bundle?) {        

super.onCreate(savedInstanceState)
		            // Perform an action with the latest item data.
		}) 
	}  
}  
  
class ListFragment : Fragment() {    // Using the activityViewModels() Kotlin property delegate from the    // fragment-ktx artifact to retrieve the ViewModel in the activity scope.
	private val viewModel: ItemViewModel by activityViewModels()    // Called when the item is clicked.    
	fun onItemClicked(item: Item) {
		// Set a new item.
		viewModel.selectItem(item)
		
		}  
}
```

> see more [here](https://developer.android.com/guide/fragments/communicate#host-activity)

#### Share data between parent-child fragments
##### Sharing viewModel scope
If you want to share data between a a parent and a child Fragment, you can do so by setting the parent fragment as the **scope for the `viewModel`**.
```kotlin
class ListFragment: Fragment() {
	private val viewModel: ListViewModel by viewModels() //<-Parent's scope
	override fun onViewCreated() {
		viewModel.data.observe(viewLifecycleOwner, Observer{ list ->
			// Listen for changes in the UI
		})
	}
}
class ChildFragment: Fragment(){
	private val viewModel: ListViewModel by
	 viewModels({requireParentFragment()}) // <- Parent's scope
	 
}
```

##### Share scope with Navigation Graph
```kotlin
class ListFragment: Fragment() {    
// Using the navGraphViewModels() Kotlin property delegate from the fragment-ktx
// artifact to retrieve the ViewModel using the NavBackStackEntry scope.  // R.id.list_fragment == the destination id of the ListFragment destination (Parent)
	private val viewModel:ListViewModel by navGraphViewModels(R.id.list_fragment)
	override fun onViewCreated(view: View, savedInstanceState: Bundle?) { 
		viewModel.filteredList.observe(viewLifecycleOwner, Observer { 
		item ->            // Update the list UI.
		}
	}  
}
```


#### Share one-time values between un hierarchy fragments

Using  [[Zettelkasten/Android Fragments#The Fragment Manager\|#The Fragment Manager]]'s `FragmentResultOwner` allows the FragmentManager to act as a central store for results. i.e
```kotlin
// Receiver
	setFragmentResultListener("requestKey") { requestKey, bundle ->        	val result = bundle.getString("bundleKey")
	// Do something with the result.    
}
	
//Sender
setOnClickListener {    
val result = "result"
setFragmentResult("requestKey", bundleOf("bundleKey" to result))  
}
```
### The Fragment Manager

[`FragmentManager`](https://developer.android.com/reference/androidx/fragment/app/FragmentManager) is the class responsible for performing actions on your app's fragments, such as adding, removing, or replacing them and adding them to the back stack.

You might never interact with `FragmentManager` directly if you're using the [Jetpack Navigation](https://developer.android.com/guide/navigation) library, as it works with the `FragmentManager` on your behalf.

#### Accessing the Manager
Fragments can host one or more child fragments. Inside a fragment, you can get a reference to the `FragmentManager` that manages the fragment's children through [`getChildFragmentManager()`](https://developer.android.com/reference/androidx/fragment/app/Fragment#getChildFragmentManager()). If you need to access its host `FragmentManager`, you can use [`getParentFragmentManager()`](https://developer.android.com/reference/androidx/fragment/app/Fragment#getParentFragmentManager()).

#### Back Stack
The `FragmentManager` manages the fragment back stack. At runtime, the `FragmentManager` can perform back stack operations like adding or removing fragments in response to user interactions

When the user taps the Back button on their device, or when you call [`FragmentManager.popBackStack()`](https://developer.android.com/reference/androidx/fragment/app/FragmentManager#popBackStack()), the top-most fragment transaction pops off of the stack. If there are no more fragment transactions on the stack, and if you aren't using child fragments, the Back event bubbles up to the activity. I

## Relates to
- [[Components\|Components]]
- [[Zettelkasten/Component Composition\|Component Composition]]
## References

[Google docs](https://developer.android.com/guide/fragments/fragmentmanager)
[Comunicate with Fragments](https://developer.android.com/guide/fragments/communicate#pass-between-fragments)