#Using Kotlin for Server-side Development

Kotlin is a great fit for developing server-side applications, allowing to write concise and expressive code while maintaining full compatibility with existing Java-based technology stacks and a smooth learning curve:

1. Expressiveness: Kotlin's innovative language features, such as its support for type-safe builders and delegated properties, help build powerful and easy-to-use abstractions.
+ Scalability: Kotlin's support for coroutines helps build server-side applications that scale to massive numbers of clients with modest hardware requirements.
+ Interoperability: Kotlin is fully compatible with all Java-based frameworks, which lets you stay on your familiar technology stack while reaping the benefits of a more modern language.
+ Migration: Kotlin supports gradual, step by step migration of large codebases from Java to Kotlin. You can start writing new code in Kotlin while keeping older parts of your system in Java.
+ Tooling: In addition to great IDE support in general, Kotlin offers framework-specific tooling (for example, for Spring) in the plugin for IntelliJ IDEA Ultimate.
+ Learning Curve: For a Java developer, getting started with Kotlin is very easy. The automated Java to Kotlin converter included in the Kotlin plugin   helps with the first steps. Kotlin Koans offer a guide through the key features of the language with a series of interactive exercises.

#Frameworks for Server-side Development with Kotlin

1. Spring makes use of Kotlin's language features to offer more concise APIs, starting with version 5.0. The online project generator allows to quickly generate a new project in Kotlin.

+ Vert.x, a framework for building reactive Web applications on the JVM, offers dedicated support for Kotlin, including full documentation.

+ Ktor is a Kotlin-native Web framework built by JetBrains, making use of coroutines for high scalability and offering an easy-to-use and idiomatic API.

+ kotlinx.html is a DSL that can be used to build HTML in a Web application. It serves as an alternative to traditional templating systems such as JSP and FreeMarker.

+ The available options for persistence include direct JDBC access, JPA, as well as using NoSQL databases through their Java drivers. For JPA, the kotlin-jpa compiler plugin adapts Kotlin-compiled classes to the requirements of the framework.

#Deploying Kotlin Server-side Applications

Kotlin applications can be deployed into any host that supports Java Web applications, including Amazon Web Services, Google Cloud Platform and more.

This blog post offers a guide for deploying a Kotlin application on Heroku.

AWS Labs provides a sample project showing the use of Kotlin for writing AWS Lambda functions.

#Users of Kotlin on the Server Side

Corda is an open-source distributed ledger platform, supported by major banks, and built entirely in Kotlin.

JetBrains Account, the system responsible for the entire license sales and validation process at JetBrains, is written in 100% Kotlin and has been running in production since 2015 with no major issues.

#Next Steps

1. The Creating Web Applications with Http Servlets and Creating a RESTful Web Service with Spring Boot tutorials show you how you can build and run very small Web applications in Kotlin.
+ For a more in-depth introduction to the language, check out the reference documentation on this site and Kotlin Koans.