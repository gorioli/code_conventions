------------------------------------
> Consistency in code style leads to much easier comprehension among teammates, quicker code reviews, and fewer bugs.

1. General notes for code styles:

The if following one line body statement is confusing for the eye and error-prone:

 ```
  if (expression) body_statement
 ```
This one is less confusing, but still is not perfect:
```
  if (expression)
    body_statement
```
This one is the most clear and provides the most git diffs updates clear:
```
  if (expression) {
     body_statement
  }
```
Articles:
1. https://google.github.io/styleguide/jsguide.html#formatting-braces
2. https://softwareengineering.stackexchange.com/questions/16528/single-statement-if-block-braces-or-no

------------------------------------
What style we should stick to?

#1:
- - - - - - - - - - - - - - - - - - -
```
if(i === -1) {
  recipients.push(value);
}
else {
  recipients.splice(i, 1);
}
```

#2:
- - - - - - - - - - - - - - - - - - -
```
i === -1 ? recipients.push(value) : recipients.splice(i, 1);
```
------------------------------------
Good conventions about react programming styles from airbnb:
https://github.com/airbnb/javascript/tree/master/react

------------------------------------
When commenting above the class of global function, follow JSDoc conventions:
https://google.github.io/styleguide/jsguide.html#jsdoc

Top two mistakes in documentation:

• Assuming people know everything
• Assuming people are stupid

------------------------------------
Do not use long lines:
https://google.github.io/styleguide/jsguide.html#formatting-column-limit
However there is exception for the strings:
https://github.com/airbnb/javascript#strings--line-length
The best is to apply a code processor like Prettier.

------------------------------------
When programmatically building up strings, use template strings instead of concatenation:
https://github.com/airbnb/javascript#es6-template-literals

------------------------------------
React Components Living Style Guides Overview:
https://www.nearform.com/blog/react-components-living-style-guides-overview/

------------------------------------
**General proposal of how to name booleans**

I find it difficult to understand:
```
let disableButton = !this.state.disableEdit;
```
It is difficult to understand because we have 2 negative words (disable is negative, enable is positive) on both sides and we use logical not `!` operator, so it looks like `negative = !negative`. It should be `positive = !negative`. 

would be much less brain power involved if we did something like this:
```
let disableButton = !this.state.enableEdit;
```
or this version:
```
let disableButton = !this.state.isTrashButtonShown;
```
Also, the best clarity is achieved when we use only positive words in boolean meaning (`isEnable = true` is better than `isDisable = false`, in the second I have to translate it to positive in my mind in order to understand).

Just food for thought to all of us, you do not need to change it Geo if you think that it's ok.

I personally think that it's easier to write a code that doesn't generate errors and harder to write the same code that is also very easy to understand. In fact, the second is the art of code :) 

Also worth mentioning that functions or variables that return or hold boolean values, should start with `is` or `was`, like `isEnabled`, `wasCalledBefore`. This convention seems to be popular in JS and other languages as well. In ruby, boolean vars are denoted with question mark instead.

------------------------------------
**The Art of Readable Code**:
 - [# 1](https://qiita.com/azarudeenjj/items/80f142e21c1cfc5b27a2), 
 - [# 2](https://qiita.com/azarudeenjj/items/9baa57735ed13ae49472).
