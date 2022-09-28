# Chapter 2 Takeaways: Meaningful Names

## Use Intention-Revealing Names
"Names should reveal intent." p.18
Should make clear "why it exists, what it does, and how it is used." p.18
"If a name requires a comment, then the name does not reveal its intent." p.18

ex.  int d; // elapsed time in days  p.18

### ex. Explicit Code
public List<int[] > getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard)
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
        return flaggedCells;
}

### ex. Increased Clarity
public List<Cell> getFlaggedCells() {
    List<Cell> flaggedCells = new ArrayList<Cell>();
    for (Cell cell : gameBoard)
        if (cell.isFlagged())
            flaggedCells.add(cell);
        return flaggedCells;
}

p.19

## Avoid Disinformation
"Programmers must avoid leaving false clues that obscure the meaning of code. We should avoid words whose entrenched meanings vary from our intended meaning." p.19

"Beware of using names which vary in small ways." p.20

### ex. Disinformation 1
a: XYZControllerForEfficientHandlingOfString
b: XYZControllerForEfficientStorageOfString

"Using inconsistent spellings is disinformation." p.20

"A truly awful example of disinformative names would be the use of lower-case L or uppercase O as variable names expecially in combination. The problem, of course, is that they look almost entirely like the constants one and zero, respectively." p. 20

### ex. Disinformation 2
int a = 1;
if ( O == 1)
    a = 01
else
    l = 01

# Make Meaningful Distinctions

"Number-series naming (a1, a2, .. aN) is the opposite of intentional naming. Such names are not disinformative--they are noninformative; they provide no clue to what the author's intention." p. 21

### ex. Intent?
public static voice copyChars (char a1[], char a2[]) {  
    for (int i = 0; i < a1.length; i++) {  
        a2[i] = a1[i];  
    }  
}  

"Noise words are another meaningless distinction. Imagine that you have a 'Product' class. If you have another called 'ProductInfo' or 'ProductData', you have made the names different without making them mean anything different. 'Info' and 'Data' are indistinct noise words like 'a', 'an', and 'the'." p. 21

"The problem comes in when you decide to call a variable 'theZork' because you already have another variable named 'zork'." p. 21

# Use Pronounceable Name
"If you can't pronounce it, you can't discuss it without sounding like an idiot." p. 22

"genymdhms" p. 22

# Use Searchable Names
"Single-letter names and numeric constants have a particular problem in that thye are not easy to locate across a body of text." p. 22

"One might easily grep for MAX_CLASSES_PER_STUDENT, but the number 7 could be more troublesome." p. 22

"In this regard, longer names trump shorter names, and any searchable name trumps a constant in code." p. 22

"My personal prefrence is that single-letter names can ONLY be used as local variables inside short methods." p. 22

# Avoid Encodings
"Encoding type or scope information into names simply adds an extra burden of deciphering." p.23

# Hungarian Notation
"Objects are strongly typed, and editing environemnts have advanced such that they detect a type error long before you can run a comple! so nowadays HN and other forms of type encoding are simply impediments." p.24

# Member Prefixes
"You also don't need to prefix member variables with m_ anymore." p. 24

# ex. Before
public class Part {
    private String m_dsc; // The textual description
    void setName(String name) {
        m_dsc = name;
    }
}

# ex. After
public class Part {
    String description;
    void setDescription(String description) {
        this.description = description;
    }
}

"Besides, people quickly learn to ignore the prefix (or suffix) to see the meaningful part of the name." p. 24

# Interfaces and Implementations

"IShapeFactory and ShapeFactory? I prefer to leave interfaces unadorned. The preceding I, so common in today's legacy wads, is a distraction at best and too much information at worst." p. 24

"So if I must encode either the interface of the implementation, I choose the implementation. Calling it ShapeFactoryImp, or even the hideous CShapeFactory, is preferable to encoding the interface." p. 24

# Avoid Mental Mapping
"Readers shouldn't have to mentally translate your names into other names they already know. This problem generally arises from a choice to use neither problem domain terms nor solution domain terms." p. 25

"One difference between a smart programmer and a professional programmer is that the professional understands that clarity is king. Professionals use their powers for good and write code that others can understand." p. 25

# Class Names
"Classes and objects should have noun or noun phrase names like Customer, WikiPage, Account, and AddressParser. Avoid words like Mangaer, Processor, Data, or Info in the name of a class. A class name should not be a verb." p.25

# Method Names
"Methods hsould have verb or verb phrase names like postPayment, deletePage, or save. Accessors, mutators, and predicates should be named for their value and prefiexed with get, set, and is according to the javabean standard." p. 25

"When constructors are overloaded, use static factory methods with names that describe the arguments." p.25

### ex. Describe Arguments
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
The above is better than
Complex fulcrumPoint = new Complex(23.0);

p.25

# Don't Be Cute
"Choose clarity over entertainment value." p. 26

"Cuteness in code often appears in the form of colloquialisms or slang." p. 26

"Say what you mean. Mean what you say."

# Pick One Word
"Pick one word for one abstract concept and stick with it. For instance, it's confusing to have fetch, retrive, and get as equivalent methods of different classes. How do you remember which method name goes with which class? Sadly, you often have to remember which company, group, or individual wrote the library or class in order to remember which term was used. Otherwise, you spend an awful lot of time browsing through headers and previous code samples." p. 26.

# Don't Pun
"Avoid using the same word for two purposes." p. 26

"So we should use a name like insert or append instead. To call the new method add would be a pun." p. 27

"Our goal, as authors, is to make our code as easy as possible to understand. We want our code to be a quick skim, not an intense study." p. 27

# Use Solution Domain Names
"Remember that the people who read your code will be programmers. So go ahead and use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth." p. 27

"The name AccountVisitor means a great deal to a programmer who is familiar with the VISITOR pattern." p. 27

# Use Problem Domain Names
"Separating solution and problem domain concepts is part of the job of a good programmer and designer. The code that has more to do with problem domain concepts should have names drawn from the problem domain." p. 27

# Add Meaningful Content
"Instead, you need to place names in context for your reader by enclosing them in well-named classes, functions, or namespaces. When all else fails, then prefixing the name may be necessary as a last resort." p. 27

### ex. Variables With Unclear Context
private void printGuessStatistics (char candidate, int count) {
    String number;
    String verb;
    String pluralModifier;
    if (count == 0) {
        number = "no";
        verb = "are";
        pluralModifier = "s";
    } else if (count == 1) {
        number = "1";
        verb = "is";
        pluralModifier = "";
    } else {
        number = Integer.toString(count);
        verb = "are";
        pluralModifier = "s";
    }
    String guessMessage = String.format (
        "There %s %s %s%s", verb, number, candidate, pluralModifier
    );
    print(guessMessage);
}

### ex. Variables Have a Context
public class GuessStatisticsMessage {
    private String number;
    private String verb;
    private String pluralModifier;

    public String make(char candidate, int count) {
        createPluralDependentMessageParts(count);
        return String.format(
            "There %s %s %s%s",
            verb, number, candidate, pluralModifier );
    }

    private void createPluralDependentMessageParts(int count) {
        if (count == 0) {
            thereAreNoLetters();
        } else if (count == 1) {
            thereIsOneLetter();
        } else {
            thereAreManyLetters(count);
        }
    }

    private void thereAreManyLetters(int count) {
        number = Integer.toString(count);
        verb = "are";
        pluralModifier = "s";
    }

    private void thereIsOneLetter() {
        number = "1";
        verb - "is";
        pluralModifier = "";
    }

    private void thereAreNoLetters() {
        number = "no";
        verb = "are";
        pluralModifier = "s";
    }
}

# Don't Add Gratuitous Context
"In an imaginary application called 'Gas Station Deluxe,' it is a bad idea to prefix every class with GSD." p. 29

"Shorter names are generally better than longer ones, so long as they are clear. Add no more context to a name than is necessary." p. 30

"The names accountAddress and customerAddress are fine names for instances of the class Address but could be poor names for classes. Address is a fine name for a class. If I need to different between MAC addresses, port addresses, and Web addresses, I might consider PostalAddress, MAC, and URI. The resulting names are more precise, which is the point of all naming." p. 30

# Final Words
"The hardest thing about choosing good names is that it requires good descriptive skills and a shared cultural background." p. 30

"You will probably end up surprising someone when you rename, just like you might with any other code improvement. Don't let it stop you in your tracks." p. 30

"If you are maintaining someone else's code, use refactoring tools to help resolve these problems. It will pay off in the short term and continue to pay in the long run." p. 30.