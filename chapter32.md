### Chapter 32: Self-Documenting Code

#### 32.1 External Documentation
* Unit Development Folder (UDF) or Software Development Folder (SDF) is a set of informal notes developers use during construction to detail design decisions at the class/package level not detailed elsewhere
* Detailed design document has low level design decisions at the class/routine level stating why certain designs were chosen and alternatives that were considered

#### 32.2 Programming Style as Documentation
* The main contributor to code level documentation isn't comments, but good programming style

#### 32.3 To Comment or Not to Comment
* Good comments don't repeat or explain the code, they clarify its intent
* Comments should explain, at a higher level of abstraction than the code, what you're trying to do
* Comments should be like a table of contents or a section heading in a technical manual so that you know where in the code to look for the details
* Because they can be outdated comments should not be taken as truth but the code should be reviewed

#### 32.4 Keys to Effective Comments
* Comments should not be used to explain difficult or tricky code because it is better to rewrite the code so that it is more understandable
* TODO comments should be removed before code is released
* Summary comments are particularly useful when someone other than the code’s original author tries to modify the code
* Intent comments describe what the original programmer was thinking when creating a section of code
* Information that can't be expressed in code comments include licenses, versions, company specific documentation, etc.
* **The three kinds of comments that are acceptable for completed code are information that can’t be expressed in code, intent comments, and summary comments**
* Guidelines for commenting efficiently
  * Use styles that don't break down or discourage modification
  * Use the Pseudocode Programming Process to reduce commenting time
  * Integrate commenting into your development style
  * **If your design is hard to code, simplify the design before you worry about comments or code**
  * Performance is not a good reason to avoid commenting because comments can be removed from production code if necessary

#### 32.5 Commenting Techniques
* Avoid endline comments except for data declarations and marking the end of blocks
* Most comments and a well-documented program or one sentence or two sentence comments that describe paragraphs of code
* **Write comments at the level of the code's intent. Describe the purpose of the block of code that follows the comment.**
  * Think of what you would name a routine that does the same thing as the block of code
* Focus your documentation efforts on the code itself by ensuring the code is self-documenting
* Focus paragraph comments on the why rather than the how
* Use comments to prepare the reader for what is to follow
* Make every comment count by avoiding excessive comments
* Use comments to document tricky techniques used instead of straightforward techniques for the purpose of performance improvement by pointing out the straightforward technique and quantifying the performance gain
* Comment anything that gets around an error or an undocumented feature in a language or an environment
* Justify violations of good programming style
* Don't comment tricky code; rewrite it
* Comment the allowable range of numeric values in data declarations
* Comment limitations on input data
* Document global data by indicating the purpose of the data and why it needs to be global
* Commenting control structures
  * Provide the reason for the if/case decision and a summary of the outcome or  indicate the purpose of the loop
  * Put a comment before each if, case, loop, or block of statements
  * Comment the end of each control structure to show what ended, this is helpful for deep nesting or long loops
  * Treat end of loop comments as a warning indicating complicated code
* Commenting routines
  * Keep comments close to the code they describe (principle of proximity)
  * Describe each routine in one or two sentences at the top of the routine, for all routines except simple accessor routines
  * Document parameters where they are declared
  * Differentiate between input and output data
  * Document interface assumptions, including assumptions about the state of variables received
  * Comment on the routine's limitations
  * Document the routine's global effects (what it does to global data)
  * Document the source of algorithms that are used
* Guidelines for class documentation
  * Describe the design approach to the class (and alternatives that were discarded)
  * Describe limitations, usage assumptions, etc
  * Comment the class interface (all public functions), at the very least
  * Don't document implementation details in the class interface
* Guidelines for file documentation
  * Describe the purpose and contents of each file
  * Include legal notices in the block comment
  * Give the file a name related to its contents
