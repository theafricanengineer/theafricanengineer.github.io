---
layout: post
title: The Rise of Modern Programming Languages
---
### Introduction

1995 was an important year in the programming community. This year, four programming languages were released that would go on to influence the programming world in ways that were not anticipated at the time of their official release. Incidentally, this was also the time that the web was just beginning to make waves and the Internet was on the verge of exploding to the mainstream.

The four languages that made their debut in 1995 were Java, JavaScript, PHP and Ruby. Although there wasn't any much fanfare accompanying their creation, these languages would eventually grow to become ubiquitous programming tools for most sofware developers. Up until that time, C and C++ were the dominant languages. Despite the fact that these two languages were very powerful, they were not inherently suited for the world-wide web. In addition they were often considered to be a little complicated and intimidating to novice programmers (especially C++).

Among the four, Java proved to be a runaway success. With its oft quoted slogan of "Write Once, Run Everywhere", Java became an intant hit as it was much easier to learn and master (compared to C++). Java also introduced a novel idea of the Java Virtual Machine (JVM), that made it possible to write programs that would be run on different platforms without the need for recompilations.

### The Need for New Programming Languages

Beginning in the 2000s, the programming landscape started changing. More and more computing machines started shipping with multiple processors and even individual processors had more than one core. This shift in computing hardware necessitated the need for programming languages that would take full advantage of the new processor architecture. Languages needed to be able to execute processes concurrently and/or in parallel in order to maximize the potential of the new multi-core processors. Concurrency was no longer an after-thought, it needed to be built into the language itself.

In recent years, there has also been a resurgent interest in functional programming, a paradigm that tries to eliminate side effects(link?) as much as possible. As a matter of fact, the occurrence of side effects has proven to be a bane in the modern programmer's life. It usually makes the process of debugging code (the one activity that every programmer dreads) far much harder. In concurrent programming, safety and immutability of data becomes an important issue. Data corruption should be kept at a minimum as much as possible.

Last but not least, modern machines have continued to grow very powerful. While in the past, much emphasis was put on the performance speeds of the programs, this focus has recently faded. Instead, much attention has shifted towards programmer productivity. As a result, it pays for a programming language to have neat and elegant syntax, which is easy to write and read. A new developer should be able to pick it up quickly and be up and running with the language in the shortest time possible. One ought to be able to play with the language right from beginning through an interactive loop, commonly known as the REPL (Read-Eval-Print Loop), without having to go through tedious setup and compilation processes.

### Teaching an Old Dog New Tricks

In order to stay relevant in the emerging programming landscape, a lot of efforts have been made to update older languages like Java and C++ to fit into the current state of affairs. In Java for example, Lambda Expressions and the Streams API were added in the Java 8 release, and Java 9 now ships with a REPL. Multithreading libraries have also been incorporated into the languages in order to enhance their concurrency abilities. The main drawback for these 'old' languages is that they were never built from the ground up to solve the emerging problems in the modern programming world. Trying to retrofit new features into the languages isn't an elegant solution either.
This leaves us with no other choice except to embrace new programming languages that have been designed from the ground up to address some of the thorny issues in modern software engineering.

### Necessity is the Mother of Invention

Due to the factors discussed above (and many others not mentioned in this article), several programming languages have been invented in order to solve some (if not all) of the problems. I call these languages 'modern programming languages' because all of the them have been released within this century.
As you will soon realize, most of these new languages have a lot in common. The syntax of some of them look very similar.

Some of the common features shared by most of the languages are:

* variables are preferred to be immutable by default
* type inference
* most of them emphasize type safety
* most of them have trailing function return types
* some of them offer easier ways of spawning multiple processes that can be executed in parallel asynchronously
* some of them offer easier ways for inter-process synchronization through channels (and similar primitives)
* most of them emphasize the functional style of programming (e.g. pattern matching and lazy evaluation)
* most of them don't require semi-colons (;) as statement terminators
* most of them offer a REPL
* most of them statically-typed
* most of them have clean and elegant syntax, without much clatter and verbosity

### Popular Modern Programming Languages

The following are arguably the most popular modern programming languages:
1. Scala
2. Golang (Go)
3. Rust
4. Kotlin
5. Swift

According to the 2017 Stackoverflow survey (link?), all of the above languages, except Kotlin, were in the top ten.
The following is an overview of some of the features of each language.
N/B: I will be using a simple function declaration to compare the five languages.

### Scala

This is a language that made its debut in the first decade of this century and is arguably one of the earliest 'modern' programming languages. It is a product from the academia. First released in 2004 by Martin Odersky who was working at the EPFL in Switzerland, Scala(link?) combines object-oriented and functional programming paradigms.
Applications written using Scala run on top of the JVM, hence they are easily portable to multiple platforms.

A simple function declaration in Scala is as follows:

	def factorial(x: Int): Int = {
	
	      // The body of the function goes here...
	
	}

A function in Scala is declared using the **def** keyword (similar to Python and Ruby). This is followed by the name of the function, in this case **factorial**, followed by a list of parameters in a pair of parentheses. Note that the parameter, in this case ***x***, is followed by a colon (**:**) and then its data type (***Int***, for an integer). If there are more than one parameter in the list, then they should be separated by a comma.
After the closing parenthesis of the function parameter list, we have another colon and an ***Int***. This is the trailing function return type (more properly called the ***result type*** in Scala).
Following the function's result type is an equals sign (**=**) and a pair of curly braces that contain the body of the function. Now, the equals sign might appear a little strange to those who are still new to Scala but it makes a lot of sense from a mathematical point of view. The contents within the curly braces may be considered as a mathematical expression that returns (or yields) a result depending on a particular set of input variables. The result would then be assigned to whatever is to the left of the equals sign. In other words, when the factorial function is called, it will '***return***' whatever the result of the **expression** within the curly braces is.

Variables in Scala are declared using either ***val*** or ***var*** keywords. Variables declared using the ***val*** keyword are immutable and therefore are not reassignable (this is the preferred option in Scala). On the other hand variables declared using the ***var*** keyword can be reassigned.
If a variable is given an initial value, then its type doesn't have to be given explicitly, the interpreter can easily 'infer' its type from the initial value:

	val x = 20

In this case the type of '***x***' will be inferred to be an integer (***Int***).
If a variable has no initial then its type must be given explicitly:

	var x: Int

In such a case, both declaration and initialization of the variable can be done simultaneously, like so:

	var x: Int = 20

***Concurrency in Scala***:

Scala uses ***Actors*** (Based on the Actor Model proposed by **Carl Hewitt** in the early 1970s) to implement concurrency. This concept is borrowed from ***Erlang***.
A simple example is shown below:

	import scala.actors.Actor
	import scala.actors.Actor._
	
	val simpleActor = actor {
	      loop {
	            receive {
	                 case s: String => println("This is a string: " + s)
	                 case i: Int => println("This is an integer: " + i.toString)
	                 case _ => println("I don't know what this is.")
	            }
	      }
	}
	
	simpleActor ! "scala is awesome"
	simpleActor ! 32
	simpleActor ! 32.134

When the code above is run, the output will be as shown below:

	This is a string: scala is awesome
	This is an integer: 32
	I don't know what this is.

The first two lines just import the **scala.actors** package together with its accompanying methods.
The line that begins with the ***val*** definition creates an **actor** called ***simpleActor*** that is able to receive messages depending on the cases expressed within the **receive** block.
An actor is a thread-like object that is able to receive and 'store' messages. Actors are usually mapped to native threads which can then be executed concurrently.
Actors communicate through passing messages to each other. To send a message to an actor, an exclamation mark or bang (**!**) is used, as shown below:

	simpleActor ! "scala is awesome"

In this case, a string message, '*scala is awesome*' is send to the **actor** '***simpleActor***'. Note that the actor is always to the left of the bang and the message is always to the right.

When an actor receives a message it tries to find a correponding match within the cases defined in the **receive** block using **pattern matching**. If no matching case is found, the default case (if any), will be executed. For example, in our sample program above, when a message containing a float (32.134) was sent to the actor, the default case was executed ("I don't know what this is"). Note the underscore (**_**) for the default case.

Every actor has a **mailbox** in which  messages sent to it are queued for further action. When an actor sends a message, it does not block, and when it receives a message, it is not interrupted.

An alternative to ***receive*** is ***react***, which unlike receive, does not return after it finds and processes a message. That is, its result type is '**Nothing**'. The advantage of using '*react*' instead of '*receive*' is that with react only a single thread is necessary (in principle) to host all of a program's actors.

One of the early adopters of Scala was **Twitter** way back in 2009.

The main drawback for Scala seems to be its steep learning curve, but once you master it, you'll wonder why you lived without it.

One of the authoritative books on Scala is Programming in Scala(Amazon link?) by Martin Odersky, Lex Spoon and Bill Venners. It is worth checking out.

### Golang

