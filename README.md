# Selenium, TestNG and JUnit Migration

Katalon Studio currently supports executing test cases from [Selenium](https://www.selenium.dev/), [TestNG](https://testng.org/doc/documentation-main.html), or [JUnit](https://junit.org/junit4/) projects. You just need to migrate them to a destination Katalon Studio project. By migrating test scripts from Selenium and TestNG/JUnit to Katalon Studio, you don't have to start everything from scratch. You can reuse your test cases and enjoy Katalon features to execute and maintain them.

This section gives instructions on how to migrate your test scripts from a Selenium and TestNG/Junit project to a Katalon project with newly supported features and keywords. Also, a sample TestNG project is provided to give you first-hand experience with our newly supported features.

Katalon Studio only supports:

* Selenium version **3.x**
* TestNG version **6.11**
* JUnit version **4.12**

Katalon Studio's new features to facilitate the migration include:

1. Supporting viewing, editing, and creating Java class files under the **Include/scripts/groovy** folder
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/java1.png" width="285" height="">


   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/java-script.png" width="501" height="">

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/new-java-class.png" width="362" height="">

2. Built-in TestNG keywords to support JUnit runner

* Run TestNG Test Classes
* Run TestNG Test Suites
* Run JUnit Test Cases

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/testng-kw.png" width="260" height="">

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/testng-kw-2.png" width="334" height="">

### runTestNGTestClasses

**Syntax**: `runTestNGTestClasses(List testClasses)`\
**Description**: run TestNG test classes and generate TestNG report at the running report folder.\
**Parameters**:

* Name: testClasses
  * Type: List
  * Description: List of TestNG classes
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

### runTestNGTestSuites

**Syntax**: `runTestNGTestSuites(List testSuites)`\
**Description**: run TestNG test suites and generate TestNG report at the running report folder.\
**Parameters**:

* Name: testSuites
  * Type: List
  * Description: List of TestNG suites as `.xml` files
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

### runJUnitTestCases

**Syntax**: `runJUnitTestCases(List testCases)`\
**Description**: run JUnit test cases and generate JUnit report at the running report folder.\
**Parameters**:

* Name: testClasses
  * Type: List
  * Description: List of JUnit test cases as classes
  * Mandatory: Required
* Name: flowControl
  * Type: FailureHandling
  * Description: an instance FailureHandling that controls the running flow
  * Mandatory: optional

## How to migrate

To migrate Selenium/TestNG/JUnit scripts to a Katalon Studio project, please do as follows:

1. Open the `.gradle` file and add Java dependencies of your Selenium/TestNG/JUnit project.
   > Katalon Studio has bundled TestNG, JUnit and Selenium dependencies, so you don't need to declare those dependencies again.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/build-gradle.png" width="629" height="">
2. Open the Command Prompt or Terminal and enter `gradle katalonCopyDependencies`, then wait for the Gradle to build successfully.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/build-success.png" width="282" height="">
3. Create a project in Katalon Studio, which is the destination for the migrated Selenium/TestNG/JUnit test cases
4. Copy and paste the source code of your Selenium/TestNG/JUnit project in the `Include/scripts/groovy` folder of your Katalon project.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/step5.png" width="322" height="">
6. Copy and paste other resources of your Selenium/TestNG/JUnit project in the root folder of your Katalon project.
7. Create a test case that includes TestNG keywords to run TestNG test suites or JUnit test classes.
   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/Selenium-TestNG-Migration/step7.png" width="629" height="">

## Usage Example

A sample project of migrating TestNG scripts to Katalon Studio is available [here](https://github.com/katalon-studio-samples/TestNG-Migration).

## Companion products

### Katalon TestOps

[Katalon TestOps](https://analytics.katalon.com) is a web-based application that provides dynamic perspectives and an insightful look at your automation testing data. You can leverage your automation testing data by transforming and visualizing your data; analyzing test results; seamlessly integrating with such tools as Katalon Studio and Jira; maximizing the testing capacity with remote execution.

* Read our [documentation](https://docs.katalon.com/katalon-analytics/docs/overview.html).
* Ask a question on [Forum](https://forum.katalon.com/categories/katalon-analytics).
* Request a new feature on [GitHub](CONTRIBUTING.md).
* Vote for [Popular Feature Requests](https://github.com/katalon-analytics/katalon-analytics/issues?q=is%3Aopen+is%3Aissue+label%3Afeature-request+sort%3Areactions-%2B1-desc).
* File a bug in [GitHub Issues](https://github.com/katalon-analytics/katalon-analytics/issues).

### Katalon Studio

Katalon Studio is an all-in-one test automation solution for Web, API, mobile, and desktop built for both beginners and expert testers.

