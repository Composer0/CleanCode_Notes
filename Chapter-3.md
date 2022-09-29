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


## Triads


## Argument Objects


## Argument Lists


## Verbs and Keywords


## Have No Side Effects


## Output Arguments


## Command Query Separation


## Prefer Exceptions to Returning Error Codes


## Extract Try/Catch Blocks


## Error Handling Is One Thing


## The Error.java Dependency Magnet


## Don't Repeat Yourself
DRY Principle.

## Structured Programming


## How Do You Write FUnctions Like THis?
"In the end, I wind up with functions that follow the rules I've laid down in this chapter. I don't write them that way to start. I don't think anyone could." p. 49

## Conclusion
"Functions are the verbs of that language, and classes are the nouns." p. 49

"The art of programming is, and has always been, the art of language design." p. 49

"Master programmers think of systems as stories to be told rather than programs to be written." p. 49