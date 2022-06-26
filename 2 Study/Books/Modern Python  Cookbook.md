# Modern Python Cookbook
Python offers us a broad set of arithmetic operators:  -, * , /, //, %, and **  .   

The / and // operators are for division; we'll look at these in a separate recipe named Choosing between true division and floor division. The ** operator raises a number to a power. 

For dealing with individual bits, we have some additional operations. We can use **&, ^, |, <<, and >>.** These operators work bit by bit on the internal binary representations of integers. These compute a binary ***AND***, a ***binary*** ***Exclusive OR***, ***Inclusive OR***, ***Left Shift***, and ***Right Shift*** respectively.

> [!note]
> It's important to note that float values are really approximations. The Python syntax allows us to write numbers as decimal values; however, that's not how they're processed internally.

>[!question] Why use floating-point?
> Two reasons: Not all computable numbers can be represented as fractions. That's why mathematicians introduced (or perhaps discovered) irrational numbers. The built-in float type is as close as we can get to the mathematical abstraction of irrational numbers. A value like √2, for example, can't be represented as a fraction. Also, float values are very fast on modern processors.

>[!note]
>When a variable's value is replaced, the previous value no longer has any references and is garbage collected. We can see this by using the id() function to track each individual string object

