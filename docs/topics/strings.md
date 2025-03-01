[//]: # (title: Strings)

Strings in Kotlin are represented by the type `String`. Generally, a string value is a sequence of characters in double quotes (`"`):

```kotlin
val str = "abcd 123"
```

Elements of a string are characters that you can access via the indexing operation: `s[i]`.
You can iterate over these characters with a `for` loop:

```kotlin
fun main() {
val str = "abcd"
//sampleStart
for (c in str) {
    println(c)
}
//sampleEnd
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

Strings are immutable. Once you initialize a string, you can't change its value or assign a new value to it.
All operations that transform strings return their results in a new `String` object, leaving the original string unchanged:

```kotlin
fun main() {
//sampleStart
    val str = "abcd"
    println(str.uppercase()) // Create and print a new String object
    println(str) // The original string remains the same
//sampleEnd
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

To concatenate strings, use the `+` operator. This also works for concatenating strings with values of other types, as long
as the first element in the expression is a string:

```kotlin
fun main() {
//sampleStart
val s = "abc" + 1
println(s + "def")
//sampleEnd
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

> In most cases using [string templates](#string-templates) or [raw strings](#raw-strings) is preferable to string concatenation.
> 
{type="note"}

## String literals

Kotlin has two types of string literals:

* [Escaped strings](#escaped-strings)
* [Raw strings](#raw-strings)

### Escaped strings

_Escaped strings_ can contain escaped characters.  
Here's an example of an escaped string:

```kotlin
val s = "Hello, world!\n"
```

Escaping is done in the conventional way, with a backslash (`\`).  
See [Characters](characters.md) page for the list of supported escape sequences.

### Raw strings

_Raw strings_ can contain newlines and arbitrary text. It is delimited by a triple quote (`"""`), contains no escaping and can contain newlines and any other characters:

```kotlin
val text = """
    for (c in "foo")
        print(c)
"""
```

To remove leading whitespace from raw strings, use the [`trimMargin()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/trim-margin.html) function:

```kotlin
val text = """
    |Tell me and I forget.
    |Teach me and I remember.
    |Involve me and I learn.
    |(Benjamin Franklin)
    """.trimMargin()
```

By default, a pipe symbol `|` is used as margin prefix, but you can choose another character and pass it as a parameter, like `trimMargin(">")`.

## String templates

String literals may contain _template expressions_ – pieces of code that are evaluated and whose results are concatenated into the string.
A template expression starts with a dollar sign (`$`) and consists of either a name:

```kotlin
fun main() {
//sampleStart
    val i = 10
    println("i = $i") // Prints "i = 10"
//sampleEnd
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

or an expression in curly braces:

```kotlin
fun main() {
//sampleStart
    val s = "abc"
    println("$s.length is ${s.length}") // Prints "abc.length is 3"
//sampleEnd
}
```
{kotlin-runnable="true" kotlin-min-compiler-version="1.3"}

You can use templates both in raw and escaped strings.

To insert the dollar sign `$` in a raw string before any symbol,
which is allowed as a beginning of an [identifier](https://kotlinlang.org/docs/reference/grammar.html#identifiers),
you can use an escape sequence `\$`:

```kotlin
val price = "\$_9.99"
```
