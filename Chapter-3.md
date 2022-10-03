# Chapter 3 Takeaways: Functions

"Functions are the first line of organization in any program." p. 31

## Small!
"The first rule of functions is that thye should be small. The second rule of functions is that they should be smaller than that." p. 34

"Every function in this program was just two, or three, or fourlines long. Each was transparently obvioius. Each told a story. And each led you to the next in a compelling order. That's how short your functions should be!" p. 34

## Blocks and Indenting
"Therefore, the indent level of a function should not be greater than one or two." p. 35

"This... makes the functions easier to read and understand." p. 35

## Do One Thing
"Functions should do one thing. They should do it well. They should do it only." p. 35

1. Determining whether the page is a test page.
2. If so, including setups and teardowns.
3. Rendering the page in HTML.
p. 35

"So, another way to know that a function is doing more than 'one thing' is if you can extract another function from it with a name that is not merely a restatement of its implementation." p. 36

## Sections within Functions
"Functions that do one thing cannot be reasonably divided into sections." p. 36

## One Level of Abstraction per Function
"In order to make sure our functions are doing 'one thing,' we need to make sure that the statements within our function are all t the same level of abstraction." p. 36

"There are concepts in there that are at a very high level of abstraction, such as getHTML(); others that are at an intermediate level of abstraction, such as : String pagePathName - PathParser.render(pagePath); and still others that are remarkably low level, such as: .append("\n")." p. 36

"Once details are mixed with essential concepts, more and more details tend to accrete within the function." p. 37

## Reading Code from Top to Bottom: The Stepdown Rule
"We want the code to read like a top-down narrative. We want every function to be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions. I call this The Stepdown Rule." p. 37

## Switch Statements
"It's hard to make a small switch statement." p. 37

"The solution to this problem is to bury the switch statement in the basement of an ABSTRACT FACTORY, and never let anyone see it. The factory will use the switch statement to create appropriate instances of the derivatives." p. 38

"They can be tolerated if they appear only once, are used to create polymorphic objects, and are hidden behind an inheritance relationship so that the rest of the system can't see them." p. 38-39

## Use Descriptive Names
"Be consistent in your names. Use the same phrases, nounds, and verbs in the function names you choose for your modules." p. 40

"The similar phraseology in those names allows the sequence to tell a story." p. 40

## Function Arguments
"The ideal number of arguments for a function is zero (niladic). Next comes (monadic), followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification--and they shouldn't be used anyway." p. 40

"The argument is at a different level of abstraction than the function name and forces you to know a detail (in other words, StringBuffer) that isn't particularly important at that point." p. 40

"Arguments are even harder from a testing point of view. Imagine the difficulty of writing all the test cases to ensure that all the various combinations of arguments work properly. If there are no arguments, this is trivial. If there's one argument, it's not too hard. With two arguments the problem gets a bit more challenging. With more than two arguments, testing every combination of appropriate values can be daunting." p. 40

"Output arguments are harder to understand than input arguments. When we read a function, we are used to the idea of information going in to the function through arguments and out through the return value.. We don't usually expect information to be going out through the arguments. So output arguments often cause us to do a double-take." p. 41

## Common Monadic Forms
"There are two very common reasons to pass a single argument into a function. You may be asking a question about that argument, as in boolean fileExists("MyFile"). Or you may be operating on that argument transforming it into something else and returning it." p. 41

"A somewhat less common, but still very useful form for a single argument function, is an event. In this form there is an input argument but no output argument. The overall program is meant ot interpret the function call as an event and use the argument to alter the state of the system." p. 41

"Using an output argument instead of a argument, the transformation should appear as the return value." p. 41

## Flag Arguments
"Passing a boolean into a function is a truly terrible practice. It immediately complicates the signature of the method, loudly proclaiming that this function does more than one thing. It does one thing if the flag is true and another if the flag is false!" p. 41

"We should have split the function into two: renderForSuit() and renderForSingleTest()." p. 41

## Dyadic Functions
"Cartesian points naturally take two arguments." p. 42

:Even obvious dyadic functions like assertEquals(expected, actual) are problematic. How many times have you put the actual where the expected should be? The two arguments have no natural ordering. The expected, actual ordering is a convention that requires practice of learn." p. 42

## Triads
"Functions that take three arguments are significantly harder to understand than dyads... I suggest you think very carefully before creating a triad." p. 42

## Argument Objects
"When a function seems to need more than two or three arguments, it is likely that some of those arguments ought to be wrapped into a class of their own."

ex. 
Circle makeCircle(double x, double y,double radius);
Circle makeCircle(point center, double radius);

## Argument Lists
"Sometimes we want to pass a variable number of arguments into a function." p. 43

"Functions that take variable arguments can be monads, dyads, or even triads." p. 43

## Verbs and Keywords
"In the case of monad, the function and argument should form a very nice verb/noun pair." p. 43


## Have No Side Effects
"Side effets are lies. Your function promises to do one thing, but it also does other hidden things." p. 44

The side effect is the call to Session.initialize(), of course. The checkPassword function, by its name, says that it checks the password. The name does not imply that it initializes the session. So a caller who believes what the name of the function says runs the risk of erasing the existing session data when he or she decides to check the validity of the user." p. 44. Refer to example on page 44 for better insight and clarity.

"This side effect creates a temporal coupling." p. 44
Temporal couplings are confusing, especially when hidden as a side effect. If you must have a temporal couping, you should make it clear in the name of the function." p. 44

## Output Arguments
"Arguments are most naturally interpreted as inputs to a function." p. 45

"Anything that forces you to check the function signature is equivalent to a double-take. It's a cognitive break that should be avoided." p. 45

"If your function must change the state of something, have it change the state of its owning object." p. 45

## Command Query Separation
"Functions should either do something or answer something, but not both." p. 45

"Functions should change the state of an object, or it should return some information about that object." p. 45

## Prefer Exceptions to Returning Error Codes
"Returning error codes from command functions is a subtle violation of command query separation." p. 46

".. lead to deeply nested structures. When you return an error code, you create the problem that the caller must deal with the error immediately." p. 46

ex.

"If you use exceptions instead of returned error codes, the the error processing code can be separeated from the happy path code and can be simplified." p. 46

ex.

## Extract Try/Catch Blocks
"Try/catch blocks are ugly in their own right. They confuse the structure of the code and mix error processing with normal processing. So it is better to extract the bodies of the try and catch blocks out into functions of their own." p. 46

ex. p. 47

## Error Handling Is One Thing
"Functions should do one thing. Error handling is one thing. Thus, a function that handles errors should do nothing else. This implies (as in the example above) that if the keyword try exists in a function, it should be the very first word in the function and that there should be nothing after the catch/finally blocks." p. 47

## The Error.java Dependency Magnet
"Classes like this are a dependency magnet; many other classes must import and use them. Thus, when the Error enum changes, all those other classes need to be recomplied and redeployed. This puts a negative pressure on the Error class. Programmers don't want to add new errors because then they have to rebuild and redeploy everything. So they reuse old error codes instead of adding new ones." p. 48

## Don't Repeat Yourself
DRY Principle.

## Structured Programming
"Following these rules means that there should only be one return statement in a function, no break or continue statements in a loop, and never, ever, any goto statements." p. 48

## How Do You Write FUnctions Like THis?
"In the end, I wind up with functions that follow the rules I've laid down in this chapter. I don't write them that way to start. I don't think anyone could." p. 49

## Conclusion
"Functions are the verbs of that language, and classes are the nouns." p. 49

"The art of programming is, and has always been, the art of language design." p. 49

"Master programmers think of systems as stories to be told rather than programs to be written." p. 49