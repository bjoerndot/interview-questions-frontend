# Question asked in the "hot seat"
Application as Frontend Developer in Germany

Not checked for errors yet. I appreciate any help. 
Sections with "..." will be filled out later.

## React
### What makes React special?
-> the state management

### Why is state management a useful tool?
-> It allows to set immutable variables (the state) in a central location (e.g. the store) that allows to access it from everywhere. Since the states are immutable, there won't be any side-effects as they can't be changed just overriden

## JavaScript
### What's new in ES6
-> arrow-functions, let & const, forEach + map + different other function for array-handling, classes

### What are classes?
-> a syntax to create javascript objects

### How was it possible to pass on objects before classes
-> prototyping chain

### What are let and const? And how do they work?
-> keywords to declare variables; `let` and `const` are block-specific and can't be accessed outside their block (in contrast to `var`). Let can be changed later while const declares a constant which is immutable. Linters will throw a warning if defining a let which is never changed

### What are arrow-functions and why should you use them?
-> arrow-functions are a different way to write functions. They don't have their own this. So they should be used in a situation, where you want to access the this of the outer scope. In situations in which you don't want to use this at all they are more useful as they can be written in one line and therefore are easier to read. You shouldn't use them as "methods". See: https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var

### What does map do?
It takes the elements of an array and applies a function to it and returns the results of that function in a new array.

### Go from const obj to const obj2:
```const obj = {"a": 1, "b": 2, "c": 3}
const obj2 = [{name: "a", value: "1"}, {name: "b": value: "2"}, {name: "c", value: "3"}]

const obj2 = Object.getOwnPropertyNames(obj).map(o => ({name: o, value: obj[o]}))
```

### With Object.keys(): how do you make sure to only get the properties of the object in question?
`Object.hasOwnProperty`

## What are imports in JavaScript?
Imports are a way to import js-code from a different file. They are called as 
```import 'NAME_OF_FILE' from 'PATH_TO_FILE';
import {'NAME_OF_VARIABLE_TO_IMPORT'} from 'PATH_TO_FILE';
```

### What is default export?
If a file should export variables it either can 
`export default … `
Or it can
`export const varName = … `

### How do you import two modules of the same name?
`import 'NAME_OF_FILE' as 'NEW_NAME' from 'PATH_TO_FILE';`

### What is happening if a "console.log(a)" is executed in the code?
The compiler checks the surrounding scope for a variable "a" that holds the content that it should log. If it is within the reachable scope for that `console.log` it prints it out, if not it will print 'not defined'

### What is a Progressive Web App?
It's an "website" that offers an offline-experience, that can be "installed" onto different devices, that is responsive, that can issue push-notifications on mobile-systems.

### What is special about push-notifications?
It's a publisher-subscriber system: the app doesn't need to pull all the time anymore.

### How do you implement a Progressive Web App in React?
....

## CSS & SASS
### What is SASS
A preprocessor

### What is the difference between mixins and functions in Sass
A function returns a value that needs to be stored in a variable while a mixin renders code in place

### What does the %-Operator do in SASS?
-> It is the placeholder-syntax. Extending it will copy the code within the %-Block but not copy the classname

### You get a stylesheet and mockups: How do you implement the input in HTML and CSS?
-> using ITCSS and BEM/OOCSS --> writing reusable modules of code

### How do you calculate specifity in CSS?
- count the number of ID attributes in the selector (= a)
- count the number of other attributes and pseudo-classes in the selector (= b)
- count the number of element names in the selector (= c)
- ignore pseudo-elements.

Aus <https://stuffandnonsense.co.uk/archives/css_specificity_wars.html> 

Another layer of specifity is !important

### When do you need to use !important?
`!important` is useful with design systems: If you need to override a value, where it is unclear at which place within the design system is defined

### What is ITCSS and how does it work?
-> ITCSS is a model to structure CSS-code to prevent specifitivity-conflicts. It separates CSS-code into different layers where the most unspecific code is on top and the more specific the code becomes the more it moves downwards. The layers are: 1) settings, 2) tools, 3) generic, 4) elements 5) objects, 6) components, 7) utilities

### What is BEM?
-> Block-Element-Modifier: A way to name classes. Objects that are one unit get a block name (e.g. `login-form`). The elements of this objects are appended to the block-name (e.g. `login-form__profile`, `login-form__inputUsername`, `login-form__inputPassword`). If any of those classes need modification it is append with -- (e.g. `login-form__inputPassword--is-wrong`)

### What is OOCSS?
-> a way to separate skin from structure in CSS (object oriented CSS). 

### What do you like better: BEM or OOCSS?
_Very preferentiell question, my answer was: BEM as it is easier to use within the HTML_

## GIT
### What's the difference between git fetch and git pull?
In the simplest terms, git pull does a git fetch followed by a git merge.
You can do a git fetch at any time to update your remote-tracking branches under refs/remotes/<remote>/.
This operation never changes any of your own local branches under refs/heads, and is safe to do without changing your working copy. I have even heard of people running git fetch periodically in a cron job in the background (although I wouldn't recommend doing this).
A git pull is what you would do to bring a local branch up-to-date with its remote version, while also updating your other remote-tracking branches.

Aus <https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch> 

## Other
### What is GraphQL
…

### What is HTML
-> a markup-langague

### Why is HTML5 not called HTML5 anymore but HTML?
-> because it is fast evovling and therefore versioning doesn't make sense