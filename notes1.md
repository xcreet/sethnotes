The `new` operator just creates a new object. What it is in depth-requires some explanation of Object-Oriented Programming, but I assume your course will get into that in time.

But for now, just think of it as a keyword to create a new "instance" of an object. In other words, it creates a new 

Here's a simple example.

`const ary = new Array();`

That creates a new array and assigns it to `ary`.

or

`const lexus = new Car();`

That creates a new copy of the Car object. An 'instance' is just a copy. You can think of `Car` as a template that we are using to make the object from.

Or here's another example -- in one of my projects I'm using an external library called 'JSZip'. I start by creating a new "instance" of JSZip.

`const zip = new JSZip();`


--------


A lot of stuff, like function expression vs. declarations, string interpolation vs. concatenation, is very much stylistic. Some people do it one way, some do it another. Lots of places will have a style guide or convention. The most important thing is understanding both. Generally people will pick what they think is more readable.

I personally much prefer to write my JS functions like this:

`function doStuff(){
    // Do stuff
}`

instead of:

`const doStuff = function() {
    // Do stuff
}`

or 

`const doStuff = () => {
    // Do stuff.
}`

To me it's simpler. But that's a personal style thing. They all basically do the same thing.

--------
I think that string concatenation is easier to understand in situations where you are combining a bunch of strings.

`const test = thing + other thing + " and that's all the things."`

String interpolation makes more sense in more complicated contexts.

Like

```
const test = `My first name is: '${firstName}' and my last name is: '${lastName}'.`
```

to me is a little simpler and more readable than:

`const test = "My first name is: '" + firstName + "'and my last name is: '" + lastName + "'"`

-------

Okay, as far as `let` and `const`...

Again, a lot of this is a style thing. I generally prefer to use `const` because I don't like to mutate variables if I don't need to. I pretty rarely find myself writing `let`.

A basic example...

```
let number = 0;
number = 2;
```

This works because we can mutate a variable defined with `let`. In the first line, we define the variable `number` and give it a value of `0`, then in the second line we change it to `2`.

However:

```
const number = 0;
number = 2;
```

This with throw an error. In the first line, we've defined the variable `number` as 0. In the second line, we try to change it, but since it's a constant, it cannot be changed.

------
As far as your `howOld` function...

Keep in mind that all the variables that you define in a function only exist inside that function. We call this "scope". As soon as the function completes, all those variables are deleted. They are restricted to the "scope" of the function. 

So the next time you run that function, it's a totally fresh slate. `yearDifference` is always calculated fresh every time the function runs, because it's within the `{}` of the function itself.