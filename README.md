# spring-boot-rest-controller-unit-test
Spring boot with JUnit 5 and Mockito

```
Spring Boot Test also provides @WebMvcTest annotation to make writing unit test for Rest Controller more simpler. 
In this tutorial, we’re gonna look at how to apply @WebMvcTest in our Spring Boot Project with JUnit 5 and Mockito.
```
```
Spring Boot @WebMvcTest annotation provides simple way to test Rest Controller,
 it disables full auto-configuration (@Component, @Service or @Repository beans will not be scanned) 
 and apply only configuration relevant to the web layer (@Controller, @ControllerAdvice, @JsonComponent, WebMvcConfigurer beans…).
```

```
Spring automatically injects the dependency into the controller.

Let’s think about the test class.

– We need to use @MockBean annotation to create and inject a mock of the TutorialRepository. 
It helps application context start), then we will set the expectations using Mockito.

```

```
– Tutorial data model class corresponds to entity and table tutorials.
– TutorialRepository handles CRUD methods and custom finder methods. It will be autowired in TutorialController and mocked in TutorialControllerTests.
– TutorialControllerTests is the main Test Class used for testing Rest Controller and annotated with @WebMvcTest.
– pom.xml contains dependencies for Spring Boot Test, Web, Spring Data, H2 database.

```
```
Let’s apply @WebMvcTest in our Spring Boot Rest API Unit Test with JUnit 5 and Mockito.

In src/test/java/com.bezkoder.spring.test, create a file with name: TutorialControllerTests.java.

Inside the file, we will define TutorialControllerTests to unit test the Rest API endpoints which has following methods:

shouldCreateTutorial(): POST /api/tutorials
shouldReturnTutorial(): GET /api/tutorials/[:id]
shouldReturnNotFoundTutorial(): GET /api/tutorials/[:id] – 404
shouldReturnListOfTutorials(): GET /api/tutorials
shouldReturnListOfTutorialsWithFilter(): GET /api/tutorials?title=[:title]
shouldReturnNoContentWhenFilter(): GET /api/tutorials?title=[:title] – 204
shouldUpdateTutorial(): PUT /api/tutorials/[:id]
shouldReturnNotFoundUpdateTutorial(): PUT /api/tutorials/[:id] – 404
shouldDeleteTutorial(): DELETE /api/tutorials/[:id]
shouldDeleteAllTutorials(): DELETE /api/tutorials
```
```
We have another way to run Junit 5 test in Spring Tool Suite with UI.
In Package Explorer, Right Click on TutorialControllerTests.java -> Run as -> JUnit
```