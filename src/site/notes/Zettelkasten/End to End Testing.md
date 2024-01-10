---
{"dg-publish":true,"permalink":"/zettelkasten/end-to-end-testing/","title":"End to End Testing","tags":["status/todo","core/tech/testing"],"created":"2023-12-15T10:13:00.660+00:00"}
---


# End to End Testing

### What is E2E testing?

Test whole workflows with a user-like interaction in a production-like environment 

#### Tools

##### Native

- Espresso
- XCUITest
###### Maestro
Pros:
- Easy to write
- Run code
- Cloud service
- CI/CD Integration
- Record

Cons:
- Lack of advanced features
###### Appium
Pros:
- Custom actions 
- Plugins

Cons:
- Hard to setup

##### Web
- Playwrite
- Cypress


#### Things to consider

+ **Multiplatform**: Allowing to run test suites that work in both platforms but allowing to write platform-specific instructions
+ **Small suite of tests** :A small and well curated suite of test that should work religiously.
+ **Reflect Figma flows**: Easy to write test based on expected outputs, like errors and success.
+ **Low dev time**: As the test suites simulate user interactions that run on top of the app, they are easy to integrate without spending too much dev time.


#### Notes








## Relates to
## References
