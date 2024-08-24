<!-- cspell: words Deno, IIFE, ufeff -->

# JavaScripting
This is an opinionated manual for people who have never programmed before to go from zero to hero programming in JavaScript.
This manual will focus on directness and simplicity, where simplicity means fewer.

This manual is not exhaustive.
It deliberately leaves much information out, perhaps most.
The goal is zero to hero.
There is much in the language a developer does not need.
If more information on unmentioned features becomes desirable people should know where to look after reading this manual.

## What is programming
Programming is the craft of writing software.
Software is a tool to achieve automation and automation is the process of eliminating labor.
If everything you do or accomplish when writing software does not seek to achieve automation you are wrong.

Reading software is much different than reading natural language.
In natural language, like novels or essays, there are too many letters and too few articles of syntax.
That can make reading natural language slow and challenging for people with low orthographic processing capacity, such as dyslexia.
In software code syntax is abundant, so many people with dyslexia find reading code not at all challenging.

Writing software, however, from a neurological perspective is exactly like writing in natural language.
The same thought processes about what to write, order of operations, planning, vocabulary, and so forth occur in exactly the same way.
If a person cannot easily write an article or an essay they will find writing software supremely challenging for exactly the same reasons with equivalent output.
If a person can easily write then programming is just a matter of practice to learn a specific type of writing.

### Falsehoods about Programming
#### Simple is easy.
Simple is not easy.
Easy is defined in terms of least effort while simple is defined in terms of less quantity.
Simplicity requires great effort to achieve after multiple drafts each with their individual refactoring effort.
Simple code might be easier for later persons to understand, but only because the prior authors took extended effort to achieve that simplicity.
Complex, or many, is far easier to achieve, because it requires less refinement and less careful extended consideration.

#### Programming is a form of math.
I have heard this a lot and its completely wrong.
Programming is far more similar to writing law than performing math.
The key constituents to programming are writing and logic and the logic is most directly practiced through argumentation.
As an example of how logic is not math see this list of [common logical fallacies](https://en.wikipedia.org/wiki/List_of_fallacies) that have nothing to do with math.

As a counter point I often program so that I do not have to perform math.
I just have to know the correct order of operations and a process to successfully test the output of a program.
For everything else I just let the computer perform math as the computer is much better at math than I am.

#### Programming must be performed in a certain way.
I see this a lot from junior developers.
This typically occurs when a developer fails to apply individual thoughts to a given software process, because they fear deviation from popular norms.
The goal is to achieve automation, not do what everybody else is doing.
I once had somebody argue that my position on executing TypeScript was incorrect but it was not the common practice even though it required less effort to write and achieved compile times possibly hundreds of times faster.
My best advise is to do what makes the most sense to you personally in any given context.
Don't ever waste your time doing something measurably inferior without a strong argument for doing it.

#### Popular software cannot be wrong because many people are using it.
This is just as common as it is wrong.
Any piece of software can be critically defective irrespective of the number of users of such software.
The common thinking is that if many people use a piece of software then somebody would have a caught some given defect before you use that given software, and is referred to as *vetted by the community*.
This is a form of bias, not qualified by evidence, that takes the form of a [bandwagon fallacy](https://en.wikipedia.org/wiki/Argumentum_ad_populum).
The quality and durability of a given software application is purely a result of the dedicated testing of that software and not the frequency of use.

#### Code style is critically important.
Code style often refers to choice of conventions and vanity of formatting.
These qualities are highly subjective and will substantially differ in preference from person to person.
What matters most is achieving software that requires less effort to read and maintain, what ever those style conventions are to whomever applies them.

From a team perspective there should be some consensus, buy in, from the team members but otherwise arbitrarily dictated by a team authority.
In a team perspective the most important consideration is uniformity such that any team member may jump in and modify some piece of code non-disruptively.
Enforcement of code style should be automated as much as possible, because otherwise the enforcement effort becomes an extension of code debt.
If a given team is not willing to spend the effort to automate their enforcement of code style then code style is just not a high priority.

Perhaps the primary reason why any developer or team might over emphasize the importance of code style is because they struggle to read and write software code.
Always remember that programming is the craft of writing software just as a novelist writes novels.
Writing software requires many skills beyond the mere legibility of minimal reading and writing just as a novelist is so much more than a person that struggles to write a few words.

#### Speed
Developers tend to believe the code they write, use, or support is fast or that solutions they disapprove of are slow.
It's all bullshit.
My experience in software has reinforced that developers rarely measure anything.
As a result developers believe all manners of incorrect things about speed and performance.
The overwhelming majority of the time these beliefs are completely unfounded and incorrect.
Worse, many, perhaps most, of those incorrect conclusions tend to be incorrect by several orders of magnitude.
There is no greater example of bias than a software developer's opinions on speed.

Accurately measuring things requires additional effort.
Because of that additional effort most developers simply do not do it.
Instead they invent fictional realities to provide themselves emotional comfort.
Any opinions about speed or performance not reinforced with evidence should be discarded and abandoned outright.
Again, it's all bullshit.

### Goals of Software
The goal of software is automation, which itself is the reduction of labor.
If everything you do in writing software is not about labor reduction you are **wrong**.

One form of labor reduction is elimination of learning.
The process to eliminate learning is called *usability*, which is to say a product becomes more intuitive such that it requires less learning time from its users.

Another form of labor reduction is elimination of repetition.
That typically means to compress many steps into fewer steps, most desirably a single step.
That can be taken further by eliminating that newly refined single step into a scheduled task the computer executes without any human intervention.

Reduction of steps and tasks is also beneficial for the developer writing the code which is referred to as code reuse.
The best way to make code reusable is to package a series of instructions into a function that can be called as necessary.
Larger tasks may comprise a larger function calling multiple other functions internally.

#### Maintenance
All things created and/or used by people, and even people themselves, require maintenance.
Maintenance is the process of reviewing, refining, and correcting a thing periodically to ensure desired operational conditions.
For example automobiles require oil changes, refueling, tire rotations, and plethora of other tasks.
Regularly servicing the automobile increases the life and desired operational status of the vehicle.
Without such regular servicing the vehicle would die and early of catastrophic failure.

Like automobiles software requires regular servicing.
Sometimes defects become apparent that require resolution.
A software developers is almost never aware of defects until the given software application is used and such usage demonstrates the defect.
That means somebody, such as the developer and/or audience, must be using the software aggressively to identify defects.

#### Test Automation
Sometimes resolutions to defects can introduce other defects.
This is called *regression*, which means taking a step back.
Regression can be especially challenging to identify in more complex software.
The solution for avoiding regression is test automation.
Test automation provides a means one computer application tests another computer application using a provided set of inputs and expecting a known set of outputs.
This allows developers to provide many tests to account for most of an application's features, which is called *test coverage*.
Provided large enough test coverage if a developer introduces regression the test automation should detect the broken feature quickly allowing the developer to provide durable updates with greater confidence.

#### Performance
Superior software developers are not necessarily smarter people or people with more knowledge of software.
Superior software developers iterate faster, which dramatically increases both speed of learning or speed of troubleshoot.
As an example if a developer is producing a product in a language with a 10 second compile time and a different developer is producing a product in a different language with a 10 minute compile time that first developer can iterate 60 times faster.
What that really means in practical terms is that this first developer can fail 59 out of 60 attempts and still be as productive as the second developer, but only if that second developer never fails.

In order to achieve superior iteration speed all steps, execution, and process in writing a piece of software must be faster.
Any time I mention speed I mean according to measures.
The more precise those measures are and the less variable those measures are the better they are.

There is a term in software development called the *mythical 10x developer*.
This describes developers capable of producing more than ten times faster than their peers.
A person does not need to be good at writing software to achieve *mythical 10x developer* status.
They just need to measure things, apply a little common sense, and ask the right questions.

## How to write software
Software can be written just about anywhere that keyboard characters appear on screen.
Writing in natural language is aided by use of tools designed to help with writing, like word processor applications, likewise a code editor aids in writing software.
Here are some current popular code editors:

* [VS Code](https://code.visualstudio.com/)
* [Notepad++](https://notepad-plus-plus.org/)
* [Sublime Text](https://www.sublimetext.com/)
* [Atom](https://atom-editor.cc/)
* [Vim](https://www.vim.org/)

I strongly recommend building some confidence with Vim.
Vim is unique in that it executes in a command terminal (command line interface).
That is valuable because if you can remotely access a computer/server via terminal, such as through SSH, you can execute Vim on that remote machine to edit code without need for any kind of remote desktop experience.

### REPL
REPL stands for read, evaluate, print, loop.
A REPL is any simple application that allows code input, evaluates that input, and then writes output to the same location.
This is an incredible way to learn a software convention with the least possible effort.
Node.js defaults to a REPL when executed without pointing to other application code.
All modern web browsers come with a REPL in the *console* tab of their embedded developer tools utility.

## JavaScript in about 60 seconds
JavaScript was designed to be a small hobby language for amateurs to sprinkle dynamic insanity into web pages.
That is a polite way of saying the language allows far too much sloppiness, which means it forgives errors that will allow code to unexpectedly fail in production.

Over the nearly 30 years of its life JavaScript has since emerged as one of the most dominate languages on the planet and executes at around half the speed of C++.
So, its fast and absolutely everywhere, both in the web browser, and in command terminals via things like [Node.js](https://nodejs.org/en) and [Deno](https://deno.com/).

Node gained popularity for high concurrency.
JavaScript is a single threaded language, which means it can only do one thing in the language at a time.
JavaScript also features a convention called the *event loop*, which is multi parallel stacktraces.
Although it can only do one thing at a time it can do something else while waiting on a prior thing.
That means that provided enough memory on the local computer JavaScript can manage many tasks executing outside the language at the same time.
The original goal was for a single JavaScript instance to manage 10,000 concurrent user sessions in a server, which had not been done before from a single application process.

## JavaScript syntax
### Characters
* Characters
   * JavaScript respects Unicode character literals in the code.
   * Any Unicode character may be referenced using the convention `\uHHHH` for UTF8 characters, or `\uHHHH\uHHHH` for UTF16 characters, `\uHHHH\uHHHH\uHHHH\uHHHH` for UTF32 characters where H is for any hexadecimal value.
      * Hexadecimal is a base-16 counting system displayed as 0-9 and a-f where a is decimal 10, b is decimal 11, c is decimal 12, d is decimal 13, e is decimal 14, and f is decimal 15.
   * Characters in JavaScript strings are [UTF16 strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#utf-16_characters_unicode_code_points_and_grapheme_clusters).
   * JavaScript has [named character escapes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape).
   * Any character can be escaped when immediately preceded by a forward slash, but be aware of named character escapes that already prefix with a forward slash.
      * My recommendation is never escape alpha characters with a forward slash to avoid confusion between named character escapes and characters escaped from syntax.
* Statement Termination
   * `;` Semicolons terminate code statements.  Semicolons are required.  If you don't add them the code interpreter will add them for you in ways you might not expect.
* Containment
   * `{}` Curly Braces.  Curly braces allow definition of object bodies, function bodies, and code blocks.  In C language these would be called: hash maps, functions, and procedures.
   * `[]` Square Braces.  Square braces allow definition of array bodies and dynamic access to objects.
   * `()` Parenthesis.  Parentheses allow grouping of logic within an expression, which is helpful to dictate order to arithmetic operations.
* White space
   * `\f\n\r\t\v\u0020\u00a0\u1680\u2000-\u200a\u2028\u2029\u202f\u205f\u3000\ufeff`.
   * White space is important for code syntax as it separates key words from each other and some white space literal characters will cause syntax errors in certain contexts.
   * New line characters terminate a code statement, in most cases.  This is due to some insanity called *Automatic Semicolon Insertion*, so for safety always insure statements are terminated with semicolons.
   * Space characters are generally safe everywhere.
* Word characters
   * `a-f`, `A-F`, `0-9`, `_`, `$`.  These characters may be used safely in variable names and property names.  Variables and property names cannot start with a number.
* Assignment
   * `=` The equal sign assigns values to variables.
   * `:` The colon character assigns values to object properties.
* Comparison
   * `===` Compares two things for value equality.
   * `<` Compares if one thing is less than a second thing.
   * `>` Compares if one thing is greater than a second thing.
* Arithmetic
   * `+` Addition
   * `-` Subtraction
   * `*` Multiplication
   * `**` Exponent
   * `/` Division
* Strings
   * `'` Single quote string literal
   * `"` Double quote string literal
   * \` String template
   * My recommendation is to just use string templates for all strings.
* Comments
   * `//` Line Comment. A line comment is terminated by a new line character.
   * `/*` Block Comment. A block comment is terminated by either the code sequence `*/` or end of file.

### Key words
* `break` Immediately exits a loop.
* `const` Declares one or more, comma separated, variables that **cannot** be reassigned.
* `do` Invokes a *do/while* loop.
* `else` Provides an alternate branch to a choice invoked from an `if` keyword.
* `export` Turns a code file into a module that can be imported by other files.
* `if` Allows a code choice by evaluating an expression.
* `import` Allows importing code modules, separate files, into a given code file.
* `function` Invokes a function.
* `let` Declares one or more, comma separated, variables that **can** be reassigned.
* `return` Immediately exits a function with a value.  If no value is specified with the return keyword the given function's output is value *undefined*.
* `while` Either invokes a *while* loop or terminates a *do/while* loop.

### Data types
#### Primitives
* BigInt - numeric values that are always positive integers.  The bigInt type allows larger values than the number data type.  bigInt values look numeric but end with a letter *n*, such as: `1234n`.
* Boolean - Values are limited to `true` or `false` for explicit comparisons.
* Number - Numeric values are for arithmetic.
* RegExp - Stores a *regular expression* pattern for pattern matching against string values.
* String - Strings store text that people read.  Strings are always wrapped in some manner of matching quotes.  `"1234"` is a string and not a number.
* **null** - A type and generic empty value that can be assigned to any variable or object property irrespective of data type.
* **undefined** - A type and value supplied to variables that never assigned a value or to functions that do not explicitly return a value.

#### Complex
* Array - An array is a list that you can iterate over.  In JavaScript arrays are variable length and each stored item may be of any data type, even complex types.
   ```javascript
   const myArray = [1234, "string", function () {
       return "x";
   }];
   ```
* Function - Functions optionally receive input, always return a single value, and otherwise store statements for execution when the given function is called.
   * Input to function is optional and is provided as arguments.
   * If output is not specified with a *return* key word the given function will simply return value **undefined**.
   * Functions are extremely portable in JavaScript in that they may be used anywhere a primitive type may be used.
     That convention is called *first-class citizens*, and most other languages do not have this.
   * Functions my optionally be assigned to a variable, may optionally be named, but will throw an error if not provided at least one of those prior forms of identity.
   ```javascript
   const myFunction = function functionName(input1, input2, inputN) {
       return "output";
   };
   ```
   * If parentheses are written immediately following a function body, the closing curly brace, that function will be executed immediately.
     This convention is called IIFE, immediately invoked function expression and is usually wrapped in an additional set of parenthesis to prevent to separate that statement from any following statement.
     In the following example the function will execute and return a value before the outer assignment completes.  
   ```javascript
   const myString = (function () {
       return "output";
   }());
   ```
* Object - An object stores key/value pairs.  The keys are always string type but the values may be any data type, event complex types.

## JavaScript conventions
### Complex types
In this language complex types can be assigned to a variable, such as:
```javascript
const myTool = function () {
    return "something";
};
```

Or, complex types can be written literally for a single use, such as:
```javascript
const myTool = function () {
    return "something";
};
const myFunctions = [myTool, function () {
    return "some value";
}];
```

In this case a function and an array are declared.  The array stores two functions: the declared function and a second function.

### Arrays
Arrays are lists of variable length and any combination of data types where each item is separated by a comma.
For example the following is perfectly valid:
```javascript
const myArray = [
    "string", 2, true, null, function () {
        return 3;
    }
];
```

All arrays features a *length* property indicating the number of items within the array.
Arrays allow iteration over their stored values using a loop and such loops can be terminated by checking for the array's length property.

Array values are referenced using a numeric index, starting from 0, in square braces, and attempts to reference an array index that does not exist will return **undefined**:
```javascript
// makes use of the prior code sample
myArray[2]; // returns boolean true
myArray[5]; // returns undefined
```

An array index can be gathered by calculation, but if the resulting value of such a calculation refers to an index not present in the array the value **undefined** is returned;
```javascript
myArray[Array[1] + 1]; // returns null, which is the fourth index in the array, or index value 3
myArray[(Array[1] * 500) / Math.pi]; // returns undefined, because such index does not exist in this array
```

### Objects
Objects store comma separated lists of key value pairs.
Here is a simple example:

```javascript
const myObj = {
    "first": 1,
    "second": 2,
    "third": 3
};
```

Values are assigned to key names using the colon character, `:`.
Key names are always string data types, but the values may be any data type, even complex types like arrays, functions, and other objects.
Each key value pair in an object is called a *property* of that object.

Object properties are typically access using dot separated reference notation.
Using the prior example we could access the object like: `myObj.first` which would return the value `1`.
That only works if a given key name conforms to the rules of JavaScript named references.

Object properties may also be accessed using the *array notation* convention making use of square braces: `myObj["first"]` which would return `1`.
Array notation allows accessing an object with variables.
Consider the following example:

```javascript
const myObj = {
    "first": 1,
    "second": 2,
    "third": 3
};
const keys = Object.keys(myObj);
let index = 0;
myObj[keys[index]]; // returns 1
```

In the above example an object is declared and a variable named *keys* is declared.
The `Object.keys` method returns an array of key names for the passed in object.
Since the variable `index` is assigned a value of 0 and the first key in the object is `first` then `keys[index]` returns `first`, the first key name of the object and that is passed as a property reference to the object via array notation.

### Lexical scope
Lexical scope refers to nesting.
With exception to objects any use of curly braces provides a section of code called a *block*, and each block provides scope.
Variables and functions declared in a given block are scoped to that block.

Since lexical scope refers to nesting different blocks may be nested.
Variables declared in a given block are available for reference everywhere in the given block including child scopes.
However, variables declared in a child scope are only available for reference in the given scope they are declared which means this given child scope and any scopes nested within this child scope.
Attempting to reference a variable from a scope higher than where the variable is declared will not work as expected because the language won't know how to resolve the reference.

The way that works in the language is that every time a reference is encountered it is resolved by first looking at the local scope and then stepping up one scope at a time until the declaration point is found.
That process is referred to as *traversing the scope chain*.
Here is a brief code example:

```javascript
function hello(x, y) {
    // a hypothetical outer scope
    // variable "a" is declared in a child scope, so you cannot reference it here
    if (x > 3) {
        let a = x + 3;
        // middle scope
        // variable "a" is available here, because this is its local scope
        // variable "x" and "y" are available here because they are declared in the parent scope
        // variable "b" is not available here because it is declared in a child scope to this scope
        if (a < 10) {
            let b = 15;
            // most inner of these three scopes
            // variables declared here will not be available to the two higher scopes
            // variables declared in the two higher scopes will be available here
            return y;
        } 
    }
}
```

Notice the code example above features three scopes where one is nested within another.
The code comments explain the three scopes and what is available where.
Also, notice where variables *x* and *y* are declared as function arguments (function inputs).
Function arguments always take the scope of the function's body.

You must also understand that lexical scope is always available in the language and cannot be disabled or altered.

## Summary
That is all there is to how I program in JavaScript.
In summary all I need is:

* Primitive data types
* operators
* scope
* loops
* objects
* arrays
* functions

Everything beyond this is just a matter of organization, calling the correct instructions in the correct order, and then maximizing code reuse where possible.

### Further Learning
This document does not cover the language's standard methods.
This will be required learning, so consider that homework.

This document also does not discuss external APIs.
External APIs scare the shit out of developers.
As somebody who struggles to find any feeling of fear I cannot relate, nor do I have sympathy.