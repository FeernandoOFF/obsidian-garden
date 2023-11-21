---
{"dg-publish":true,"permalink":"/zettelkasten/android-instrumentation-testing/","title":"Android Instrumentation Testing","tags":["status/todo","core/tech/android"],"noteIcon":"","created":"2023-10-11T13:10:04.657+01:00"}
---


# Android Instrumentation Testing

> [See more](https://developer.android.com/codelabs/basic-android-kotlin-compose-write-automated-tests?continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-compose-unit-2-pathway-3%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-compose-write-automated-tests#4)
- Create a `androidTest/java` folder inside your `src` directory
- Create a *package* by right-clicking and selecting `New -> Package`
- Create a Kotlin file 
--
```kotlin
import androidx.compose.ui.test.junit4.createComposeRule
import org.junit.Rule

class TipUITests {
// Declared compose instance
	@get:Rule   
	val composeTestRule = createComposeRule()

// Declare test
@Test
fun calculate_20_percent_tip() {
    composeTestRule.setContent {
        TipTimeTheme {
           TipTimeScreen()
        }
    }
	}

// Performe actions
composeTestRule.onNodeWithText("Bill Amount")
	.performTextInput("10")   
// Performe actions
composeTestRule.onNodeWithText("Tip (%)")
.performTextInput("20")   

val expectedTip = NumberFormat.getCurrencyInstance().format(2)

composeTestRule.onNodeWithText("Tip Amount: $expectedTip")
//Assertion
	.assertExists("No node with this text was found.")

}
```





## Relates to
## References
