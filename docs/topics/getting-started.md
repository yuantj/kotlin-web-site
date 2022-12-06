[//]: # (title: Get started with Kotlin)

[Kotlin](https://kotlinlang.org) is a modern but mature programming language designed to make developers happier.
It's concise, safe, interoperable with Java and other languages, and provides many ways to reuse code between multiple platforms for productive programming.

Pick it up now to start building powerful applications!

## Install Kotlin

Kotlin is included in each [IntelliJ IDEA](https://www.jetbrains.com/idea/download/) and [Android Studio](https://developer.android.com/studio) release. Download and install one of these IDEs to start using Kotlin.

> IntelliJ IDEA Community Edition is free to use for personal and commercial development.
> 
{type=note}

## Run your first Kotlin program

Below are some examples of Kotlin code that you can try. Click **Run** or copy the code to run in [Playground](https://play.kotlinlang.org/).

<tabs>
<tab id="simple" title="Simple">

```kotlin
fun main() {
    val name = "stranger"        // Declare your first variable
    println("Hi, $name!")        // ...and use it!
    print("Current count:")
    for (i in 0..10) {           // Loop over a range from 0 to 10
        print(" $i")
    }
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

</tab>

<tab id="functional" title="Functional">

```kotlin
fun main() {
    // Who sent the most messages?
    val frequentSender = messages
        .groupBy(Message::sender)
        .maxByOrNull { (_, messages) -> messages.size }
        ?.key                                                 // Get their names
    println(frequentSender) // [Ma]

    // Who are the senders?
    val senders = messages
        .asSequence()                                         // Make operations lazy (for a long call chain)
        .filter { it.body.isNotBlank() && !it.isRead }        // Use lambdas...
        .map(Message::sender)                                 // ...or member references
        .distinct()
        .sorted()
        .toList()                                             // Convert sequence back to a list to get a result
    println(senders) // [Adam, Ma]
}

data class Message(                                          // Create a data class
    val sender: String,
    val body: String,
    val isRead: Boolean = false,                              // Provide a default value for the argument
)

val messages = listOf(                                       // Create a list
    Message("Ma", "Hey! Where are you?"),
    Message("Adam", "Everything going according to plan today?"),
    Message("Ma", "Please reply. I've lost you!"),
)
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

</tab>
</tabs>

Congratulations! You've taken your first steps with Kotlin.

## Learn how to speak Kotlin

If there's one document you must read, it's our page on Kotlin's [basic syntax](basic-syntax.md). This page takes you through an example program and explains in a concise and simple way how Kotlin is structured and written.

## Expand your knowledge

Now that you can parse Kotlin code, we have some recommended learning materials based on your experience.

<deflist collapsible="true">
 <def title="I'm new to programming">
   <p>If Kotlin is your first programming language, we recommend:</p>
   <ul>
      <li>Signing up for the free Kotlin Basics track on JetBrains Academy.</li>
      <li>Reading the Atomic Kotlin book.</li>
   </ul>
 </def>
 <def title="I'm a Java developer">
   <p>If you have Java development experience, we recommend that you read about:</p>
   <ul>
      <li>Basic types</li>
      <li>Control flow</li>
      <li>Functions</li>
      <li>Classes</li>
      <li>Null safety</li>
   </ul>
   <p>We also recommend reading our migration guides on:</p>
   <ul>
     <li>Strings</li>
     <li>Collections</li>
     <li>Nullability</li>
   </ul>
   <p>In addition, there is a course available on Coursera that shows the similarities and differences between Kotlin and Java: Kotlin for Java developers.</p>
 </def>
 <def title="I'm an experienced developer in another language">
   <p>If you have development experience in another language, we recommend that you read about:</p>
   <ul>
      <li>Basic types</li>
      <li>Control flow</li>
      <li>Functions</li>
      <li>Classes</li>
      <li>Null safety</li>
   </ul>
   <p>We also recommend investigating the API references for our libraries:</p>
   <ul>
     <li>Standard library</li>
     <li>Coroutines library</li>
     <li>Serialization library</li>
   </ul>
 </def>
</deflist>

But you don't have to follow our recommendations. For a complete list of all our learning materials, see [Learning materials overview](learning-materials-overview.md).

## Learn about the platforms Kotlin supports

Kotlin can be used with many different platforms. Read more in the platform links below to continue your Kotlin journey.

* [Multiplatform](multiplatform.md)
* [Android](android-overview.md)
* [Native](native-overview.md)
* [JVM](jvm-get-started.md)

## Get support

Have questions or need some help? You can reach us through these channels:
* Talk to us on ![Slack](slack.svg){width=25}{type="joined"}Slack. [Get an invite](https://surveys.jetbrains.com/s3/kotlin-slack-sign-up) and join the [#getting-started](https://kotlinlang.slack.com/archives/C0B8MA7FA) channel.
* Raise an issue on our [issue tracker](https://youtrack.jetbrains.com/issues/KT).

Or you can join our ![StackOverflow](stackoverflow.svg){width=25}{type="joined"}StackOverflow community by subscribing to the ["kotlin" tag](https://stackoverflow.com/questions/tagged/kotlin), to see if your question has already been answered.


What do you think of our get started guide? [Share your feedback](https://surveys.hotjar.com/d82e82b0-00d9-44a7-b793-0611bf6189df).
